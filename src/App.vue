<template>
  <div id="app">
    <main-container />
  </div>
</template>

<script>
import axios from "axios";
import MainContainer from "./components/MainContainer.vue";

export default {
  name: "App",
  components: {
    MainContainer,
  },
  data() {
    return {
      discs: [],
    };
  },
  mounted() {
    axios
      .get("https://flynn.boolean.careers/exercises/api/array/music")
      .then((response) => {
        this.discs = response.data;
      });
  },
};
</script>

<style lang="scss">
#app {
}
</style>
