<script>

import movie from '../components/movie.vue'
import addMovie from '../components/addMovie.vue'
import AddMovie from '../components/addMovie.vue';

export default {
  data(){
    return {
      allMovies:[]
      
    }
  },
    components: { movie, addMovie},

    methods: {
      async getMovies() {
        try{
          const res = await fetch("https://koamoment2.onrender.com/movie");
          const data = await res.json();
          this.allMovies = data;
        } catch(error){
          console.error( error);
        }
    },

      async deleteMovie(_id) {
        try{
          const res = await fetch("https://koamoment2.onrender.com/movie/" + _id, {
            method: "DELETE",
            headers: {
              "Accept": "application/json",
              "Content-type": "application/json"
             }
          });
          const data = await res.json();

          this.getMovies();
          
        } catch(error) {
          console.error(error)
        }
      }
  
  //slutar methods
  },

    mounted() {
      
      this.getMovies();
    }

  }

</script>

<template>
<div>
    <addMovie/>
  </div>

  
  <main>
    <div>
      <h1>Filmer</h1>
      <div id="divMovie">
    <movie @deleteMovie="deleteMovie(movie._id)" v-for="movie in allMovies" :movie="movie" :key="movie._id"/>
    </div>
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
    text-align: center;
    text-decoration:underline;
  }

  #divMovie {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
  }

  @media (min-width: 600px) {
  #divMovie {
    display: grid;
    grid-template-columns: repeat(2, 1fr); 
  }
}
}

</style>
