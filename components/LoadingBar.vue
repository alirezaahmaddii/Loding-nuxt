<template>
  <transition name="fade">
    <div v-if="loading" class="loading-page">
      <div class="loading">
        <div class="logo">
          <svg xmlns="http://www.w3.org/2000/svg" style=" margin: auto; background: none; display: block; shape-rendering: auto;" width="197px" height="197px" viewBox="0 0 100 100" preserveAspectRatio="xMidYMid">
            <circle cx="84" cy="50" r="10" fill="#febe02">
              <animate attributeName="r" repeatCount="indefinite" dur="1.3888888888888886s" calcMode="spline" keyTimes="0;1" values="8;0" keySplines="0 0.5 0.5 1" begin="0s"></animate>
              <animate attributeName="fill" repeatCount="indefinite" dur="5.5555555555555545s" calcMode="discrete" keyTimes="0;0.25;0.5;0.75;1" values="#febe02;#febe02;#febe02;#febe02;#febe02" begin="0s"></animate>
            </circle><circle cx="16" cy="50" r="10" fill="#febe02">
            <animate attributeName="r" repeatCount="indefinite" dur="5.5555555555555545s" calcMode="spline" keyTimes="0;0.25;0.5;0.75;1" values="0;0;8;8;8" keySplines="0 0.5 0.5 1;0 0.5 0.5 1;0 0.5 0.5 1;0 0.5 0.5 1" begin="0s"></animate>
            <animate attributeName="cx" repeatCount="indefinite" dur="5.5555555555555545s" calcMode="spline" keyTimes="0;0.25;0.5;0.75;1" values="16;16;16;50;84" keySplines="0 0.5 0.5 1;0 0.5 0.5 1;0 0.5 0.5 1;0 0.5 0.5 1" begin="0s"></animate>
          </circle><circle cx="50" cy="50" r="10" fill="#febe02">
            <animate attributeName="r" repeatCount="indefinite" dur="5.5555555555555545s" calcMode="spline" keyTimes="0;0.25;0.5;0.75;1" values="0;0;8;8;8" keySplines="0 0.5 0.5 1;0 0.5 0.5 1;0 0.5 0.5 1;0 0.5 0.5 1" begin="-1.3888888888888886s"></animate>
            <animate attributeName="cx" repeatCount="indefinite" dur="5.5555555555555545s" calcMode="spline" keyTimes="0;0.25;0.5;0.75;1" values="16;16;16;50;84" keySplines="0 0.5 0.5 1;0 0.5 0.5 1;0 0.5 0.5 1;0 0.5 0.5 1" begin="-1.3888888888888886s"></animate>
          </circle><circle cx="84" cy="50" r="10" fill="#febe02">
            <animate attributeName="r" repeatCount="indefinite" dur="5.5555555555555545s" calcMode="spline" keyTimes="0;0.25;0.5;0.75;1" values="0;0;8;8;8" keySplines="0 0.5 0.5 1;0 0.5 0.5 1;0 0.5 0.5 1;0 0.5 0.5 1" begin="-2.7777777777777772s"></animate>
            <animate attributeName="cx" repeatCount="indefinite" dur="5.5555555555555545s" calcMode="spline" keyTimes="0;0.25;0.5;0.75;1" values="16;16;16;50;84" keySplines="0 0.5 0.5 1;0 0.5 0.5 1;0 0.5 0.5 1;0 0.5 0.5 1" begin="-2.7777777777777772s"></animate>
          </circle><circle cx="16" cy="50" r="10" fill="#febe02">
            <animate attributeName="r" repeatCount="indefinite" dur="5.5555555555555545s" calcMode="spline" keyTimes="0;0.25;0.5;0.75;1" values="0;0;8;8;8" keySplines="0 0.5 0.5 1;0 0.5 0.5 1;0 0.5 0.5 1;0 0.5 0.5 1" begin="-4.166666666666666s"></animate>
            <animate attributeName="cx" repeatCount="indefinite" dur="5.5555555555555545s" calcMode="spline" keyTimes="0;0.25;0.5;0.75;1" values="16;16;16;50;84" keySplines="0 0.5 0.5 1;0 0.5 0.5 1;0 0.5 0.5 1;0 0.5 0.5 1" begin="-4.166666666666666s"></animate>
          </circle>
          </svg>
        </div>
      </div>
    </div>
  </transition>
</template>

<script>
export default {
  data: () => ({
    loading: false,
  }),
  methods: {
    start() {
      this.loading = true;
    },
    finish() {
      this.loading = false;
    },
  },
};
</script>

<style lang="scss" scoped>
.loading-page {
  background: rgba(0, 0, 0, 0.7);
  //backdrop-filter: blur(4px);
  position: fixed;
  width: 100%;
  height: 100vh;
  z-index: 10000;
  top: 0;
  left: 0;
  display: flex;
  justify-content: center;
  align-items: center;

  .loading {
    display: flex;
    flex-flow: column;
    align-items: center;
    justify-content: center;

    .logo {
      position: relative;

      svg {
        width: 120px;
        height: 120px;
        overflow: unset;

        .pt-l {
          animation: ptL 1.5s infinite alternate ease-in-out;
        }

        .pt-r {
          animation: ptR 1.5s infinite alternate ease-in-out;
        }

        .pt-t {
          animation: ptT 1.5s infinite alternate ease-in-out;
        }

        .pt-b {
          animation: ptB 1.5s infinite alternate ease-in-out;
        }

      }

      @keyframes ptL {
        from {
          transform: translate(-30px, 0);
        }
        to {
          transform: translate(0, 0);
        }
      }

      @keyframes ptR {
        from {
          transform: translate(30px , 0);
        }
        to {
          transform: translate(0, 0);
        }
      }

      @keyframes ptT {
        from {
          transform: translate(0, -30px);
        }
        to {
          transform: translate(0, 0);
        }
      }

      @keyframes ptB {
        from {
          transform: translate(0, 30px);
        }
        to {
          transform: translate(0, 0);
        }
      }
    }

    p {
      color: #d2d6ef;
      font-size: 14px;
      font-weight: 500;
      word-spacing: -3px;
      margin-top: 1rem;
    }
  }
}
</style>
