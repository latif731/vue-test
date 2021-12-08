<template>
<!-- eslint-disable max-len -->
 <div class="flex justify-center items-center h-screen w-full">
      <div
        class="
          bg-white
          shadow-md
          h-96
          mx-3
          rounded-3xl
          flex flex-col
          justify-around
          items-center
          overflow-hidden
          sm:flex-row sm:h-52 sm:w-3/5
          md:w-96
        "
      >
        <img
          class="h-1/2 w-full sm:h-full sm:w-1/2 object-cover"
          :src="product.images[0]"
          alt="image"
        />

        <div
          class="
            flex-1
            w-full
            flex flex-col
            items-baseline
            justify-around
            h-1/2
            pl-6
            sm:h-full sm:items-baseline sm:w-1/2
          "
        >
          <div class="flex flex-col justify-start items-baseline">
            <h1 class="text-lg font-normal mb-0 text-gray-600 font-sans">
              {{product.title}}
            </h1>
          </div>
          <div class="w-full flex justify-between items-center">
            <h1 class="font-bold text-gray-500">Rp. {{product.price}}</h1>
            <router-link :to="`/detail/${product.id}`">
            <button
              class="bg-gray-700 mr-5 text-white px-3 py-1 rounded-sm shadow-md"
            >
              View
            </button>
            </router-link>
          </div>
        </div>
      </div>
    </div>
</template>

<script>
import { defineComponent } from 'vue';

export default defineComponent({
  props: ['product'],

});
</script>

<style>
img{
  width: 10px;
}
</style>
