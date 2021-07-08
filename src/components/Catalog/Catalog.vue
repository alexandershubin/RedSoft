<template>
  <div class="catalog">
    <h1 class="title-h1 title-h1--catalog">Картины эпохи Возрождения</h1>
    <ul class="ul-list">
      <CatalogItem
          v-for="(paint) in paintings"
          :key="paint.id"
          :paint="paint"
          @handleBuy="handleBuy(paint.id)"
      />
    </ul>
  </div>
</template>

<script>
import CatalogItem from "./Catalog-item";
import axios from "axios";

export default {
  name: "Catalog",
  components: {CatalogItem},
  props: {},
  data() {
    return {
      paintings: [
        {
          id: 1,
          img: 'painting-4.png',
          title: '«Рождение Венеры»',
          author: 'Сандро Боттичелли',
          priceDiscount: 1000000,
          price: 2000000,
          isSold: false,
          loading: false,
          isBasket: false
        },
        {
          id: 2,
          img: 'painting-2.png',
          title: '«Тайная вечеря»',
          author: 'Леонардо да Винчи',
          priceDiscount: 3000000,
          price: 0,
          isSold: false,
          loading: false,
          isBasket: false
        },
        {
          id: 3,
          img: 'painting-3.png',
          title: '«Сотворение Адама»',
          author: 'Микеланджело',
          priceDiscount: 5000000,
          price: 6000000,
          isSold: false,
          loading: false,
          isBasket: false
        },
        {
          id: 4,
          img: 'painting-1.png',
          title: '«Урок анатомии»',
          author: 'Рембрандт',
          priceDiscount: 0,
          price: 0,
          isSold: true,
          loading: false,
          isBasket: true
        },
      ]
    }
  },
  mounted() {
    if (localStorage.getItem('paintings')) {
      try {
        this.paintings = JSON.parse(localStorage.getItem('paintings'));
      } catch (e) {
        localStorage.removeItem('paintings');
      }
    }
  },
  methods: {
    handleBuy(id) {
      const painting = this.paintings.find(item => item.id === id);
      painting.loading = true;
      return axios('https://jsonplaceholder.typicode.com/posts/1 ', {
        method: "GET"
      })
      .then(() => {
        setTimeout(() => {
          painting.isBasket = true
          const parsed = JSON.stringify(this.paintings);
          localStorage.setItem('paintings', parsed);
          painting.loading = false;
        }, 2000)
      })
      .catch((error) => {
        console.error('Что-то пошло не так :(');
        return error;
      })
    }
  }
}
</script>
