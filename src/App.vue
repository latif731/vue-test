<template>
  <div class="app" :class='mode'>
    <Header :mode ="mode"/>
    <!-- <Home/> -->
    <router-view />
  </div>
</template>

<script>
import { defineComponent } from 'vue';
import Header from './components/Header.vue';

export default defineComponent({
  components: {
    Header,
  },
  data() {
    return {
      mode: 'dark',
    };
  },
});
</script>

<style>
*{
  margin: 0;
  padding: 0;
}

.app {
  width: 100vw;
  min-height: 100vh;
  background: #F3F3F3;
  color: #15202B;
}

.dark{
  background: #192734;
  color: #F3F3F3;
}

</style>
