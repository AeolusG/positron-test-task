<template>
  <div class="card-wrapper">
    <img :src="getImageUrl" />
    <h2 class="card-wrapper__title">Просмотренные товары</h2>
  </div>
</template>

<script>
export default {
  props: {
    image: {
      type: String,
      default: null,
    },
  },
  computed: {
    getImageUrl() {
      return new URL(`../assets/images/${this.image}`, import.meta.url);
    },
  },
};
</script>

<style lang="scss" scoped>
.card-wrapper {
  display: flex;
  justify-content: space-between;
  align-items: center;
}
.card-wrapper__title {
  font-family: 'Lato Regular', sans-serif;
  font-size: 30px;
  color: rgba(31, 36, 50, 1);
  margin-bottom: 70px;
}
.products-wrapper__pagination {
  display: flex;
  align-items: center;
}
</style>
