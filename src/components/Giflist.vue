<template>
  <Gif v-for="gif in gifs" :key="gif.id" :gif="gif" />
</template>

<script>
import Gif from "./Gif.vue"
export default {
  name: "Giflist",
  components: {
        Gif,
  },
  props: {
    gifs: ['gifs'],
  },
};
</script>
