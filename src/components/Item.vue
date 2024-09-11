<template>
  <div class="Item">
    <h3>{{ item.name }}</h3>
    <p>{{ item.description }}</p>
    <p>Price: ${{ item.price }}</p>
    <button @click="addToCart">Add to Cart</button>
  </div>
</template>

<script>
export default {
  name: 'Item',
  props: {
    item: {
      type: Object,
      required: true,
    },
  },
  methods: {
    addToCart() {
      this.$emit('add-to-cart', this.item);
    },
  },
};
</script>

<style scoped>
.Item {
  border: 1px solid #ddd;
  padding: 16px;
  margin-bottom: 16px;
}
.Item h3 {
  margin-top: 0;
}
.Item button {
  margin-top: 10px;
}
</style>
