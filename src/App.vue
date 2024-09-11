<script>
import ItemList from './components/ItemList.vue'

export default {
  name: 'App',
  components: { ItemList },
  data() {
    return {
      isShowing: false,
      searchedItem: '',
      searchedProducts: [],
      products: [
        { id: 111, name: 'ringmaster', price: 120 },
        { id: 112, name: 'aghashards', price: 3020 },
        { id: 113, name: 'powerthreads', price: 3030 },
        { id: 114, name: 'rosian', price: 24200 },
        { id: 115, name: 'creep', price: 991239 },
        { id: 116, name: 'boots', price: 312130 },
        { id: 117, name: 'blinkdagger', price: 312310 },
        { id: 118, name: 'vengeful', price: 312130 },
        { id: 119, name: 'Aghanims', price: 5120 }
      ]
    }
  },
  computed: {
    searchData() {
      return this.products.filter((product) =>
        this.searchedItem
          ? product.name.toLowerCase().includes(this.searchedItem.toLowerCase())
          : false
      )
    }
  },
  methods: {
    toggle() {
      this.isShowing = !this.isShowing
    }
  }
}
</script>

<template>
  <div class="top">
    <input type="text" v-model="searchedItem" placeholder="Search for an item" />
  </div>

  <div v-if="isShowing">
    <ItemList :products="searchData" />
  </div>

  <div class="btn-div">
    <button @click="toggle">{{ isShowing ? 'Hide' : 'Show' }}</button>
  </div>
</template>

<style scoped>
.top {
  text-align: center;
}

.btn-div {
  margin-top: 50px;
  text-align: center;
}

button {
  padding: 10px 25px;
  color: #077bee;
  border: none;
  margin: center;
  transition: 0.3s ease-in-out;
}
</style>
