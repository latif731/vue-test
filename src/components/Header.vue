<template>
<!-- eslint-disable max-len -->
  <link href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/5.11.2/css/all.min.css" rel="stylesheet">
  <div class="w-screen flex flex-row items-center p-1 justify-between shadow-xs header fixed">
    <div class="ml-8 text-lg hidden md:flex"><Toggle :mode="mode"/></div>
    <span class="w-screen md:w-1/3 h-10 bg-gray-200 cursor-pointer border border-gray-300 text-sm rounded-full flex">
      <input type="text" name="serch" placeholder="Search" v-model="search"
        class="flex-grow px-4 rounded-l-full rounded-r-full text-sm focus:outline-none text-black">
      <i class="fas fa-search m-3 mr-5 text-lg text-gray-700 w-4 h-4">
      </i>
    </span>
    <div class="flex flex-row-reverse mr-4 ml-4 md:hidden">
      <i class="fas fa-bars"></i>
    </div >
      <div class="flex flex-row-reverse mr-8 hidden md:flex">
        <div class="text-gray-700 text-center bg-gray-400 px-4 py-2 m-2">Login</div>
        <div class="text-gray-700 text-center bg-gray-400 px-4 py-2 m-2">Logout</div>
      </div>
  </div>
<div v-for="product in filteredProducts" :key="product.id">
  <home :product='product'></home>
  </div>
</template>

<script>
import { defineComponent } from 'vue';
import Home from '../views/Home.vue';
import mockData from '../mock-data.json';
import Toggle from './Toggle.vue';

export default defineComponent({
  components: {
    Home,
    Toggle,
  },
  data() {
    return {
      search: '',
      products: mockData,
      mode: 'dark',
    };
  },
  computed: {
    filteredProducts() {
      return this.products.filter((product) => product.title.match(this.search));
    },
  },

});
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

.dark header{
  background: #15202B
}

</style>
