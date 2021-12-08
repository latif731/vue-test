<template>
<main>
  <h1>Product Detail {{ $route.params.id}}</h1>
  <h2>{{$route.params.title}}</h2>
  <img src="../../public/img/charger-1.jpg"/>
</main>
</template>

<script>
import { defineComponent } from 'vue';
import mockData from '../mock-data.json';

export default defineComponent({
  data() {
    return {
      products: mockData,
    };
  },
  props: {
    id: [Number, String],
  },
  computed: {
    product() {
      return mockData.find((product) => product.id === parseInt((this.id), 10));
    },
  },
});
</script>

<style>

</style>
