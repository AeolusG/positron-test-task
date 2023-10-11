<template>
  <header class="header">
    <img class="header__image" src="../assets/images/Vector.svg" alt="basket" />
    <div>
      <div class="header__content--description">Ваша корзина</div>
      <div class="header__content--items-count">{{ itemsCount }} товара</div>
      <div class="header__content--total-price">{{ itemsTotalPrice }} ₽</div>
    </div>
  </header>
</template>

<script>
export default {
  props: {
    itemsCount: {
      type: Number,
      default: null,
    },
    itemsTotalPrice: {
      type: Number,
      default: null,
    },
  },
};
</script>

<style lang="scss" scoped>
@import '/home/olya/rabstol/тестовые задания/positron-test-task/assets/fonts/fonts.css';
.header {
  width: 1280px;
  display: flex;
  justify-content: flex-end;
}
.header__content--description {
  font-family: 'Lato Regular', sans-serif;
  font-size: 14px;
}
.header__content--items-count {
  color: rgba(121, 123, 134, 1);
  font-family: 'Lato Regular', sans-serif;
  font-size: 12px;
  line-height: 17px;
}
.header__image {
  margin-right: 15px;
}
.header__content--total-price {
  font-family: 'Lato Regular', sans-serif;
  font-size: 12px;
  font-weight: 400;
  line-height: 17px;
  color: rgba(31, 36, 50, 1);
}
</style>
