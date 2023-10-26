<template>
  <div class="wrappper">
    <div class="block__img">
      <img :src="cardData.imgSrc" class="logoImg" />
    </div>
    <div class="wrapper__information">
      <div class="block__informarion">
        <a :href="cardData.link" class="informationTittle">{{
          cardData.title
        }}</a>
        <p class="informationDiscount">
          Ваша економія: <span class="discount">{{ userDiscount }}₴</span>
        </p>
        <s class="informationOldPrice">{{ cardData.oldPrice }}₴</s>
      </div>
      <div class="orderBlock">
        <p class="currentPrice">
          {{ cardData.price }}<span class="currencyLogo">₴</span>
        </p>
        <button class="buyBtn">Купити</button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name:'ProductCard',
  props: {
    cardData: {
      type: Object,
      default: () => ({}),
    },
  },
  computed: {
    userDiscount() {
      return this.cardData.oldPrice - this.cardData.price;
    },
  },
};
</script>

<style lang="css" scoped>
p {
  margin: 0;
  padding: 0;
}
.wrappper {
  width: 50%;
  display: flex;
  justify-content: center;
  border-bottom: 1px solid rgb(213, 212, 212);
}
.block__img {
  width: 25%;
}
.logoImg {
  width: 100%;
}
.wrapper__information {
  padding: 0 0 15px 15px;
  width: 50%;
  text-align: left;
}

.informationTittle {
  text-decoration: none;
  color: #0073e6;
  font-weight: 500;
}
.informationTittle:hover {
  text-decoration: underline;
  color: #ff7400;
}
.informationDiscount {
  font-size: 10px;
}
.discount {
  color: red;
}
.informationOldPrice {
  font-size: 15px;
  color: grey;
}
.orderBlock {
  display: flex;
  justify-content: space-between;
}
.currentPrice {
  font-size: 25px;
  color: red;
}
.currencyLogo {
  font-size: 10px;
}
.buyBtn {
  color: white;
  background-color: rgb(10, 164, 54);
  border: 0;
  border-radius: 5px;
  padding: 0px 15px;
  transition: transform 0.2s ease;
}
.buyBtn:hover {
  transform: scale(1.1);
}
</style>