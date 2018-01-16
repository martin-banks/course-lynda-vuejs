<template>
  <div id="app">
    <router-view 
      :products="products"
      :title="title"
    ></router-view>
  </div>
</template>

<script>
import ProductList from './ProductList.vue'
export default {
  name: 'app',
  components: {
    'product-list': ProductList,
  },
  data () {
    return {
      msg: 'Welcome to Your Vue.js App',
      title: 'Product list title',
      products: [],
    }
  },
  created() {
    $.getJSON('https://hplussport.com/api/products')
      .done(data => this.products = data)
  }
}
</script>

<style scoped>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

h1, h2 {
  font-weight: normal;
}

ul {
  list-style-type: none;
  padding: 0;
}

li {
  display: inline-block;
  margin: 0 10px;
}

a {
  color: #42b983;
}
</style>
