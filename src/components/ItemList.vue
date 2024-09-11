<script>
import Item from './Item.vue'
export default {
  name: 'ItemList',
  props: ['products'],
  components: { Item },
  data() {
    return {}
  },
  methods: {}
}
</script>

<template>
  <div class="item-list">
    <h2>Product List</h2>
    <div class="list-container">
      <Item v-for="product in products" :key="product.id" :product="product" />
    </div>
  </div>
</template>

<style scoped>
.item-list {
  max-width: 550px;
  margin: 30px auto;
  padding: 20px;
  background-color: peachpuff;
  border-radius: 10px;
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
}

.list-container {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  gap: 20px;
}

h2 {
  font-size: 24px;
  font-weight: bold;
  margin-bottom: 10px;
}

.item {
  background-color: #fff;
  padding: 10px;
  border-radius: 10px;
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
}
</style>
