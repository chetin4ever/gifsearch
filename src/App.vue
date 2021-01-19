<template>
  <Search @gifs-fetched="onFetch" />
  <gif-list :gifs="gifs" />
</template>

<script>
import GifList from "./components/GifList.vue";
import Search from "./components/Search.vue";

export default {
  name: "App",
  components: { Search, GifList },
  data() {
    return {
      gifs: [],
    };
  },
  methods: {
    onFetch(result) {
      this.gifs = result;
    },
  },
};
</script>

<style>
* {
  box-sizing: border-box;
}
body {
  padding: 50px;
  background: rgb(230, 228, 228);
}
</style>
