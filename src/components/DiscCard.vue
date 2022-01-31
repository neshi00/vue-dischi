<template>
  <div class="disc-box">
    <img :src="disc.poster" />
  </div>
</template>

<script>
export default {
  props: {
    disc: Object,
  },
};
</script>

<style lang="scss" scoped>
.disc-box {
  width: calc(100% / 5);

  img {
    width: 100%;
  }
}
</style>
