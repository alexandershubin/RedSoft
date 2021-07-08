<template>
  <nav class="nav">
    <ul class="nav-list">
      <NavItem
          v-for="(nav, index) in navigation"
          :key="index"
          :nav="nav"
      />
    </ul>
  </nav>
</template>

<script>
import NavItem from "./Nav-item";

export default {
  name: "Navigation",
  components: {NavItem},
  data() {
    return {
      navigation: ['Каталог', 'Доставка', 'Оплата', 'Контакты', 'О галерее']
    }
  },
  methods: {}
}
</script>
