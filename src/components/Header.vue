<template>
  <header class="header">
    <div class="header__wrapper">
      <div class="content wrapper">
        <img class="header__logo"
             src="../assets/img/logo-museum.png"
             height="48"
             width="48"
             alt="logo">
        <Navigation/>
        <div class="extra extra__header">
          <input class="extra__input"
                 placeholder="Поиcк по названию картинки"
          >
          <button class="btn btn__brown">Найти</button>
        </div>
      </div>
    </div>
  </header>
</template>

<script>
import Navigation from "./Navigation/Navigation";

export default {
  name: "Header",
  components: {Navigation},
  methods: {}
}
</script>

