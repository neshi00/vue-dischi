<template>
  <div class="container">
    <select @change="$emit('search', selected)" v-model="selected">
      <option value="all">All</option>
      <option v-for="(genre, index) in list" :key="index" :value="genre">
        {{ genre }}
      </option>
    </select>
  </div>
</template>

<script>
export default {
  props: {
    list: Array,
    // array riempito in App.vue tramite funzione/computed genreArray
    // e poi visualizzato in FilterBox tramite props
  },
  data() {
    return {
      selected: "all",
    };
  },
};
</script>

<style lang="scss" scoped>
.container {
  background-color: #1e2d3b;
  display: flex;
  justify-content: center;
  select {
    margin: 20px 0;
  }
}
</style>
