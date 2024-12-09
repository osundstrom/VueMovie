<script>

import movie from '../components/movie.vue'

export default {
  data(){
    return {
      allMovies:[]
      
    }
  },
    components: { movie},

    methods: {
      async getMovies() {
        try{
          const res = await fetch("https://koamoment2.onrender.com/movie");
          const data = await res.json();
          this.allMovies = data;
          console.log(allMovies)
        } catch(error){
          console.error( error);
        }
    }},

    mounted() {
      
      this.getMovies();
    }

  }

</script>

<template>


  
  <main>
    <div>
      <h1>Filmer</h1>

    <movie v-for="movie in allMovies" :movie="movie" :key="movie._id"/>
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
