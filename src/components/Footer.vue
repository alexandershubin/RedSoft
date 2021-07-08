<template>
  <footer class="footer">
    <div class="footer__wrapper">
      <div class="content wrapper">
        <img class="header__logo"
             src="../assets/img/logo-museum-footer.png"
             height="48"
             width="48"
             alt="logo">
        <Navigation/>
        <div class="extra extra__footer">
          <a href="tel:84955555555" class="extra__phone">+7 (495) 555-55-55</a>
          <span class="extra__address">г. Москва, ул. Расплетина, 24</span>
        </div>
      </div>
    </div>
  </footer>
</template>

<script>
import Navigation from "./Navigation/Navigation";

export default {
  name: "Footer",
  components: {Navigation}
}
</script>

