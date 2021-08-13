<template>
  <div id="app">
    <MainLayout/>
  </div>
</template>

<script>
  
  // @ is an alias to /src
  import MainLayout from '@/layouts/MainLayout.vue'
  
  export default {
    name: 'App',

    components: {
      MainLayout
    }
  }
</script>

<style lang="scss">
  @import '@/assets/styles/index.scss';
  
  #app {
    font-family: Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
  }

</style>
