<template>
  <div id="app">
    <header>
      <h1>My Product Store</h1>
    </header>
    <main>
      <ItemList :products="products" @add-to-cart="handleAddToCart" />
    </main>
  </div>
</template>

<script>
import ItemList from './components/ItemList.vue';

export default {
  name: 'App',
  components: {
    ItemList,
  },
  data() {
    return {
      products: [
        { id: 1, name: 'Shirt', description: 'Graphic tees', price: 2 },
        { id: 2, name: 'Shorts', description: 'Denim shorts', price: 5 },
        { id: 3, name: 'Caps', description: 'Baseball caps', price: 10 },
      ],
    };
  },
  methods: {
    handleAddToCart(product) {
      console.log('Added to cart:', product);
    },
  },
};
</script>

<style scoped>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  text-align: center;
  color: #000000;
  margin-top: 60px;
}

header {
  background-color: #bdbdcc;
  padding: 20px;
  margin-bottom: 20px;
}

main {
  padding: 20px;
}

body {
  background-color: rgb(17, 18, 19);
}
</style>