<template>
  <div class="products-wrapper">
    <h2 class="products-wrapper__title">Просмотренные товары</h2>
    <div class="products-wrapper__pagination">
      <img src="../assets/images/arrowleft.svg" />
      <div>1/6</div>
      <img src="../assets/images/arrowright.svg" />
    </div>
  </div>
  <div class="products-wrapper__card-container"></div>
  <TheProductCard v-for="card in cards" :image="card.img" />
</template>

<script>
export default {
  data() {
    return {
      cards: [
        {
          cardId: 1,
          price: 12644,
          totalCount: 1,
          totalPrice: 12644,
          img: 'hoodbig1.png',
        },
        {
          cardId: 2,
          price: 12644,
          totalCount: 1,
          totalPrice: 12644,
          img: 'hoodbig2.png',
        },
        {
          cardId: 3,
          price: 12644,
          totalCount: 1,
          totalPrice: 12644,
          img: 'hoodbig3.png',
        },
      ],
    };
  },
};
</script>

<style lang="scss" scoped>
.products-wrapper {
  display: flex;
  justify-content: space-between;
  align-items: center;
}
.products-wrapper__title {
  font-family: 'Lato Regular', sans-serif;
  font-size: 30px;
  color: rgba(31, 36, 50, 1);
  margin-bottom: 70px;
}
.products-wrapper__pagination {
  display: flex;
  align-items: center;
}
.products-wrapper__card-container {
  display: flex;
  width: 300px;
}
</style>
