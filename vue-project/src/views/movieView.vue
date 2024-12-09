<script>

import movie from '../components/movie.vue'

export default {
  data(){
    return {
      allMovies:[
        {
        id: 0,
        name: "test1",
        ImdbRating: 1,
        watched: true
        },
        {
        id: 1,
        name: "test2",
        ImdbRating: 2,
        watched: true
        },
        {
        id: 2,
        name: "test3",
        ImdbRating: 3,
        watched: true
        }
      ]
    }
  },
    components: { movie}
  }
    

</script>

<template>


  
  <main>
    <div>
      <h1>Filmer</h1>

    <movie v-for="movie in allMovies" :movie="movie" :key="movie.id"/>
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
