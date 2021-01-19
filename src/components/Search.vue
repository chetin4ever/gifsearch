<template>
  <input
    placeholder="Type someting to search for awesome gifs"
    @input="onInput"
    v-model="search"
  />
</template>

<script>
name: "Search";
export default {
  data() {
    return {
      search: "",
      timeout: "",
    };
  },
  methods: {
    onInput() {
      clearTimeout(this.timeout);
      this.timeout = setTimeout(() => {
        this.search1();
      }, 500);
    },
    search1() {
      fetch(
        `https://api.giphy.com/v1/gifs/search?api_key=dUpjhiQjVy83pI2cJnTH1aFA28HxkjYH&q=${this.search}&limit=9`
      )
        .then((response) => response.json())
        .then((result) => {
          console.log(result);
          //   this.gifs = result.data;
          this.$emit("gifs-fetched", result.data);
        });
      // dUpjhiQjVy83pI2cJnTH1aFA28HxkjYH
    },
  },
};
</script>

<style scoped>
input {
  padding: 10px 16px;
  border-radius: 4px;
  font-size: 18px;
  outline: 0;
  border: 2px solid #5f5f5f;
  display: block;
  width: 100%;
}
input:focus {
  border-color: #0078e0;
}
</style>