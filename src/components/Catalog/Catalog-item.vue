<template>
  <li class="li-item" v-bind:class="{sold: paint.isSold}">
    <img class="li-item__img"
         width="280"
         height="160"
         :src=" require('../../assets/img/' + paint.img)" alt="product">
    <div class="li-item__content">
      <h2 class="title-h2">{{ paint.title }}</h2>
      <h2 class="title-h2">{{ paint.author }}</h2>
      <div class="li-item__footer" v-if="!paint.isSold">
        <div class="price">
          <h6 class="title-h6 title-h6__throw" v-if="paint.price !== 0">{{ paint.price }}  $</h6>
          <h3 class="title-h3" v-if="paint.priceDiscount !== 0">{{ paint.priceDiscount }}  $</h3>
        </div>
        <button class="btn btn__brown btn--basket" v-if="paint.isBasket">В корзине</button>
        <button class="btn btn__brown" v-else @click="handleBuy">
          <div class="lds-ring" v-if="paint.loading"><div></div><div></div><div></div><div></div></div>
          <span v-else>Купить</span>
        </button>
      </div>
      <h3 class="title-h3 title-h3--sold li-item__footer" v-else>Продана на аукционе</h3>
    </div>
  </li>
</template>

<script>

export default {
  name: "Catalog-item",
  props: {
    paint: {
      type: Object,
      isBasket: localStorage.getItem("isBasket"),
      default() {
        return {}
      }
    },
  },
  methods: {
    handleBuy() {
      this.$emit('handleBuy')
    },
  },
}
</script>

