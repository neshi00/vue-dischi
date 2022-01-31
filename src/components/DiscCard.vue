<template>
  <div class="discs-container">
    <div class="card">
      <img :src="disc.poster" />
      <h3>{{ disc.title }}</h3>
      <div>
        <p>{{ disc.author }}</p>
        <p>{{ disc.year }}</p>
      </div>
    </div>
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
.discs-container {
  width: calc(100% / 5);

  .card {
    height: 400px;
    padding: 15px;

    margin: 10px 20px;
    background-color: #2e3a46;
    text-align: center;
    position: relative;

    img {
      width: 100%;
      height: 200px;
      object-fit: contain;
    }
    h3 {
      padding: 10px 0;
      font-weight: bold;
      font-size: 30px;
      color: #fff;
    }
    div {
      position: absolute;
      transform: translate(-50%, -50%);
      bottom: 0;
      left: 50%;
      color: #77787a;
    }
  }
}
</style>
