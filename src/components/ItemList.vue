<template>
  <div class="item-list">
    <Item
      v-for="product in products"
      :key="product.id"
      :item="product"
      @add-to-cart="addToCart"
    />
  </div>
</template>

<script>
import Item from './Item.vue';

export default {
  name: 'ItemList',
  props: {
    products: {
      type: Array,
      required: true,
    },
  },
  components: {
    Item,
  },
  methods: {
    addToCart(item) {
      this.$emit('add-to-cart', item);
    },
  },
};
</script>

<style scoped>
.item-list {
  display: flex;
  flex-wrap: wrap;
  gap: 16px;
}
</style>