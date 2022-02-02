<template>
  <div class="container">
    <select @change="$emit('search', selected)" v-model="selected">
      <option value="all">All</option>
      <option value="rock">Rock</option>
      <option value="metal">Metal</option>
      <option value="jazz">Jazz</option>
      <option value="pop">Pop</option>
    </select>
  </div>
</template>

<script>
export default {
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
