  <template>
    <div>
      <div v-for="item in jack">
        <span>
          {{item.title}}
        </span>
      </div>
    </div>
  </template>

  <script>
  export default {
    data: () => ({
      jack:[],
    }),
    methods: {
      async getData() {
        try {
          this.$nextTick(() => this.$nuxt.$loading.start());
          const res = await this.$axios.$get('/posts');
          this.jack = res;
          this.$nextTick(() => this.$nuxt.$loading.finish());

        } catch (e) {
          this.$nextTick(() => this.$nuxt.$loading.finish());
        }
      },

    },
    mounted() {
      this.getData();
    }
  }
  </script>
