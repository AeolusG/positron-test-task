<template>
  <div class="wrapper">
    <TheHeader :itemsCount="itemsTotal" :itemsTotalPrice="getTotalSum" />
    <div class="wrapper__items-in-basket">
      <div class="wrapper__breadcrumbs">
        <div class="wrapper__breadcrumbs-text">Главная</div>
        <img src="./assets/images/arrow.svg" />
        <div
          class="wrapper__breadcrumbs-text wrapper__breadcrumbs-text--active"
        >
          Корзина
        </div>
      </div>
      <div class="title">
        <div class="title__items--flex">
          <h1 class="title__items---header-typography">Ваша корзина</h1>
          <div class="title__items--count-typography">4 товара</div>
        </div>

        <div class="title__items--clean-typography">Очистить корзину</div>
      </div>
    </div>
    <TheItem
      v-for="card in cards"
      :price="card.price"
      @get-items-count="getItemsCount"
      @get-decreased="getDecreased"
      @count-total-price=""
    ></TheItem>
  </div>
</template>

<script>
export default {
  data() {
    return {
      itemsTotal: 1,
      cards: [
        {
          cardId: 1,
          price: 12644,
        },
        {
          cardId: 2,
          price: 25288,
        },
      ],
    };
  },
  methods: {
    getItemsCount(items) {
      this.itemsTotal = items + 1;
    },
    getDecreased(items) {
      this.itemsTotal = items - 1;
    },
    countTotal(count) {},
  },
  computed: {
    getTotalSum() {
      let i = 0;
      return this.cards.reduce(function (accumulator, currentValue) {
        return accumulator + currentValue.price;
      }, i);
    },
  },
};
</script>

<style lang="scss" scoped>
.wrapper {
  width: 1280px;
  margin: auto;
}
.wrapper__items-in-basket {
  width: 800px;
}
.wrapper__breadcrumbs {
  font-family: 'Lato Regular', sans-serif;
  font-size: 14px;
  line-height: 21px;
  display: flex;
  margin-bottom: 40px;
  img {
    margin-right: 10px;
  }
}
.wrapper__breadcrumbs-text {
  margin-right: 10px;
}
.wrapper__breadcrumbs-text--active {
  color: rgba(121, 123, 134, 1);
}
.title {
  display: flex;
  align-items: baseline;
  justify-content: space-between;

  margin-bottom: 40px;
}
.title__items--flex {
  display: flex;
  align-items: baseline;
}
.title__items---header-typography {
  color: rgba(31, 36, 50, 1);
  font-family: 'Lato Regular', sans-serif;
  font-size: 44px;
  font-weight: 700;
  margin-right: 20px;
}
.title__items--count-typography {
  font-family: 'Lato Regular', sans-serif;
  font-size: 18px;
  font-weight: 400;
  line-height: 26px;
  color: rgba(121, 123, 134, 1);
}
.title__items--clean-typography {
  font-family: 'Lato Regular', sans-serif;
  font-size: 14px;
  font-weight: 400;
  line-height: 21px;
  color: rgba(121, 123, 134, 1);
  text-decoration: underline;
}
</style>
