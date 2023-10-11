<template>
  <div class="card">
    <slot name="image"></slot>
    <img src="../assets/images/hood1.png" />

    <div class="card__content">
      <h3 class="card__content-title">Вытяжное устройство G2H</h3>
      <div class="card__description">
        12-72/168 м3/ч / гидрорегулируемый расход / от датчика присутствия
      </div>
      <div class="card__article">Артикул: G2H1065</div>
    </div>

    <div class="card__btn-group">
      <button @click="decreaseItems(itemsCount), countTotalPrice(itemsCount)">
        -
      </button>
      <div>{{ itemsCount }}</div>
      <button @click="increaseItems(itemsCount), countTotalPrice(itemsCount)">
        +
      </button>
    </div>

    <div class="card__price">{{ getPrice }}₽</div>
  </div>
</template>

<script>
export default {
  props: {
    title: {
      type: String,
      default: null,
    },
    description: {
      type: String,
      default: null,
    },
    partNumber: {
      type: String,
      default: null,
    },
    price: {
      type: Number,
      default: null,
    },
  },
  data() {
    return {
      itemsCount: 1,
      totalPrice: null,
    };
  },
  methods: {
    increaseItems(count) {
      this.itemsCount++;
      this.$emit('getItemsCount', count);
    },
    decreaseItems(count) {
      this.itemsCount--;
      this.$emit('getDecreased', count);
    },
    countTotalPrice(count) {
      this.totalPrice = this.price * count;
      this.$emit('countTotalPrice', count);
    },
  },
  computed: {
    getPrice() {
      let currentPrice = this.price;

      return currentPrice.toLocaleString('ru-RU');
    },
  },
};
</script>

<style lang="scss" scoped>
@import '/home/olya/rabstol/тестовые задания/positron-test-task/assets/fonts/fonts.css';
.card {
  display: flex;
  width: 800px;
  justify-content: space-between;
  align-items: center;
  border-bottom: 1px solid rgba(196, 196, 196, 1);
  padding-bottom: 20px;
}
.card__content {
  width: 300px;
}
.card__btn-group {
  display: flex;
  align-items: center;
  div {
    background: rgb(246, 248, 250);
    color: rgb(51, 55, 78);
    padding: 8px;
    margin: 5px;
    width: 20px;
    text-align: center;
  }
  button {
    border: none;
    background: rgb(246, 248, 250);
    color: rgb(51, 55, 78);
    font-size: 30px;
    padding: 10px;
    height: 34px;
    width: 34px;
    cursor: grab;
  }
}
.card__description {
  font-family: 'Lato Regular', sans-serif;
  font-size: 12px;
  font-weight: 400;
  line-height: 17px;
  margin-bottom: 20px;
}
.card__content-title {
  font-family: 'Lato Regular', sans-serif;
  font-size: 16px;
  font-weight: 600;
  line-height: 23px;
}
.card__price {
  font-family: 'Lato Bold', sans-serif;
  font-size: 18px;
  line-height: 26px;
}
.card__article {
  font-family: 'Lato Bold', sans-serif;
  font-size: 14px;
  font-weight: 400;
  line-height: 21px;
  color: rgba(121, 123, 134, 1);
}
</style>
