<template>
  <div class="gif" :style="`background-image:url(${gif.images.original.url})`">
    <input
      type="text"
      ref="url"
      readonly
      :value="gif.images.original.url"
      style="flex: 1"
    />
    <button @click="copyUrl">copy</button>
  </div>
</template>

<script>
export default {
  props: {
    gif: Object,
  },
  data() {
    //console.log(this.gif.images.original.url);
    return {};
  },
  methods: {
    copyUrl() {
      this.$refs.url.select();
      document.execCommand("copy");
      this.$refs.url.value = "copied!!!";
    },
  },
};
</script>

<style  scoped>
.gif {
  width: 240px;
  height: 240px;
  background-repeat: none;
  background-size: cover;
  margin: 20px;
  display: flex;
  justify-content: space-between;
  align-items: flex-end;
}
.gif input {
  border: none;
  padding: 10px;
}
.gif button {
  border: none;
  padding: 10px;
  background: #0078e0;
  font-weight: bold;
  color: #2c3e79;
}
</style>>
