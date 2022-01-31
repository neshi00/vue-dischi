<template>
  <div class="macro-container">
    <div class="container">
      <disc-card v-for="(disc, index) in discs" :key="index" :disc="disc" />
    </div>
  </div>
</template>

<script>
import DiscCard from "./DiscCard.vue";

export default {
  components: {
    DiscCard,
  },
  props: {
    discs: Array,
  },
};
</script>

<style lang="scss" scoped>
.macro-container {
  background-color: #1e2d3b;

  .container {
    width: 1200px;
    margin: 0 auto;
    display: flex;
    flex-wrap: wrap;
    padding: 30px 0;
  }
}
</style>
