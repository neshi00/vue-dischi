<template>
  <div id="app">
    <header-box />
    <filter-box @search="filterMusic" />
    <main-container :discs="filteredDiscs" />
  </div>
</template>

<script>
import axios from "axios";
import MainContainer from "./components/MainContainer.vue";
import FilterBox from "./components/FilterBox.vue";
import HeaderBox from "./components/HeaderBox.vue";

export default {
  name: "App",
  components: {
    MainContainer,
    FilterBox,
    HeaderBox,
  },
  data() {
    return {
      discs: [],
      filteredDiscs: [],
    };
  },
  mounted() {
    axios
      .get("https://flynn.boolean.careers/exercises/api/array/music")
      .then((response) => {
        console.log(response.data);
        this.discs = response.data.response;
        this.filteredDiscs = response.data.response;
      });
  },
  methods: {
    filterMusic(genre) {
      this.filteredDiscs = this.discs.filter((disc) => {
        return disc.genre.toLowerCase() === genre || genre === "all";
      });
    },
  },
};
</script>

<style lang="scss">
@import "./style/ClassUtility.scss";
</style>
