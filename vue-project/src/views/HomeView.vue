<script>

import movie from '../components/movie.vue'

export default {
    components: {movie}
  }

</script>

<template>


 
  <main>
    <div>
    <h1>Filmer</h1>
    <p>Vem gillar inte att titta på en bra film? Jag gör det i alla fall</p>
  </div>
  </main>
  
</template>

<style scoped>

main{
  margin-top: 2vh;
  display: flex;
  align-items: center;
  justify-content: center;
  div{
    display: block;
    max-width: 90vw;
    
  };
  h1{
    text-align: left;
  }
}


</style>
