<template>
  <div id="app">
    <header-box />
    <main-container :discs="discs" />
  </div>
</template>

<script>
import axios from "axios";
import MainContainer from "./components/MainContainer.vue";
import HeaderBox from "./components/HeaderBox.vue";

export default {
  name: "App",
  components: {
    MainContainer,
    HeaderBox,
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
        console.log(response.data);
        this.discs = response.data.response;
      });
  },
};
</script>

<style lang="scss">
@import "./style/ClassUtility.scss";
</style>
