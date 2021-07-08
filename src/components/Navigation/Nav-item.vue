<template>
  <li class="nav-item">
    <a class="nav-item__link" href="#">{{ nav }}</a>
  </li>
</template>

<script>
export default {
  name: "Nav-item",
  props: {
    nav: {
      type: String,
      default() {
        return String
      }
    }
  }
}
</script>
