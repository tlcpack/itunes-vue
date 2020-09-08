<template>
  <div>
    <div class="container">
      <h2 class="label">Search iTunes: </h2>
      <input class="text" type="text" v-model="term" @keyup.enter="exe">
      <input class="submit" type="submit" value="Search" @click="exe">
    </div>
  </div>
</template>

<script>
import axios from "axios";
export default {
  data() {
    return {
      term: "",
    }
  },
  methods: {
    async exe() {
      this.$emit("loadStart")
      const { data } = await axios.get(`//itunes.apple.com/search?term=${this.term}`);
      this.$emit("loadComplete", { results: data.results })
    },
  },
};
</script>

<style scoped>
.container {
  display: flex;
  justify-content: center;
  height: 70px;
  padding: 20px;
  background-color: #35495e;
  box-sizing: border-box;
}
.label {
  color: lightcyan;
  margin-right: 2rem;
}
.text {
  width: 50%;
  max-width: 300px;
  padding: .5em;
  border: none;
}
.submit {
  padding: .5em 2em;
  margin-left: 10px;
  color: #fff;
  background-color: #42b883;
  border: none;
  border-radius: 20px;
}
</style>