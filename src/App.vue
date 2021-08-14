<template>
  <div id="app">
    <MainLayout/>
  </div>
</template>

<script>
  
  // @ is an alias to /src
  import MainLayout from '@/layouts/MainLayout.vue'
  import { objectFitImages } from '@/assets/scripts/ofi.min.js'
  
  export default {
    name: 'App',

    components: {
      MainLayout
    },

    mounted() {
      var someImages = document.querySelectorAll('.js-ofi-polyfill');
      console.log(someImages)
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
