<script>
import { RouterLink, RouterView } from 'vue-router';
import Footer from './components/Footer.vue'
import headerNav from './components/headerNav.vue'


export default {
    components: {headerNav, Footer}
  }

</script>

<template>
  <div>
  <headerNav/>

  <RouterView/>

  <Footer/>

</div>
</template>

<style scoped>
  div{
    overflow-x: hidden;
  }
</style>
