<template>
  <div id="gifList">
    <gif v-for="gif in gifs" :key="gif.id" :gif="gif" />
  </div>
</template>

<script>
import Gif from "./Gif.vue";
export default {
  components: { Gif },
  props: {
    gifs: Array,
  },
};
</script>

<style scoped>
#gifList {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
}
</style>