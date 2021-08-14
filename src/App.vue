<template>
  <div id="app">
    <MainLayout/>
  </div>
</template>

<script>
  import MainLayout from '@/layouts/MainLayout.vue'
  import { objectFitImages } from '@/assets/scripts/ofi.min.js'
  
  export default {
    name: 'App',

    components: {
      MainLayout
    },

    mounted() {
      const someImages = document.querySelectorAll('.js-ofi-polyfill');
      objectFitImages(someImages);
    }
  }
</script>

<style lang="scss">
  @import '@/assets/styles/index.scss';
  
  #app {
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;

    .js-ofi-polyfill {
      object-fit: cover;
	    font-family: 'object-fit: cover;';
    }
  }

</style>
