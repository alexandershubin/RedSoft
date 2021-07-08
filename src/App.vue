<template>
  <div class="container">
    <Header/>
    <div class="wrapper">
      <Catalog/>
    </div>
    <Footer/>
  </div>
</template>

<script>

import Catalog from "./components/Catalog/Catalog";
import Header from "./components/Header";
import Footer from "./components/Footer";

export default {
  name: 'App',
  components: {Footer, Header, Catalog},
  methods: {}
}
</script>
