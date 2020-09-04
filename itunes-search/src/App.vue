<template>
  <v-app>
    <v-content>
      <Search />
    </v-content>
  </v-app>
</template>

<script>
import Search from "./components/Search.vue";

export default {
  components: {
    Search,
  },
};
</script>

<style>
.application {
  background-color: #a4508b !important;
  background-image: linear-gradient(326deg, #a4508b 0%, #5f0a87 74%) !important;
}
</style>
