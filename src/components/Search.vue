<template>
  <section class="h-50 p-8">
    <div class="appearance-none max-w-xl mx-auto">
      <input
        v-model="keyword"
        @input="onInput"
        class="
          w-full
          h-16
          border-2
          text-white
          border-slate-400
          focus:border-2 focus:border-slate-300
          appearance-none
          bg-transparent
          px-3
          rounded-lg
          mb-8
          focus:outline-none focus:shadow-outline
          text-xl
          px-8
          shadow-lg
        "
        type="search"
        placeholder="Type something to search for awesome gifs..."
      />
    </div>
  </section>
</template>


<script>
export default {
  name: "Search",
  data() {
    return {
      keyword: "",
      timeout: null,
    };
  },
  methods: {
    onInput() {
      clearTimeout(this.timeout);
      this.timeout = setTimeout(() => {
        this.search();
      }, 500);
    },
    search() {
      fetch(
        `https://api.giphy.com/v1/gifs/search?api_key=tJBnKnjbaCKiwH33rfUgW51MkqO1WKhJ&q=` +
          this.keyword +
          `&limit=12&offset=0&rating=r&lang=en`
      )
        .then((response) => response.json())
        .then((result) => {
          console.log(result);
          this.$emit("search", result);
        });
    },
  },
};
</script>
