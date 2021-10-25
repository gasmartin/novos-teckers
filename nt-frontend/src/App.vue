<template>
  <div id="app">
    <Header />
    <ProductPage />
  </div>
</template>

<script>
import Header from './components/Header.vue'
import ProductPage from './pages/ProductPage.vue'

export default {
  name: 'App',
  components: {
    Header,
    ProductPage
  }
}
</script>

<style>
html, body {
  overflow: hidden;
}

#app {
  height: 100vh;
}
</style>
