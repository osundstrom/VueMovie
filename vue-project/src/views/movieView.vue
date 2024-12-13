<script>

//imports
import movie from '../components/movie.vue'
import addMovie from '../components/addMovie.vue'


export default { //export
  data(){
    return {
      allMovies:[] //array för o lagar data
      
    }
  },
    components: { movie, addMovie}, //komponenter

    methods: { //methods
      async getMovies() { //funktion för att hämta filmer
        try{
          const res = await fetch("https://koamoment2.onrender.com/movie"); //hämtar 
          const data = await res.json(); //vsaret
          this.allMovies = data; //sätter allmovies till svaret(data)
        } catch(error){//vid error
          console.error( error);
        }
    },

      async deleteMovie(_id) { //funktion radera baserat på _id
        try{
          const res = await fetch("https://koamoment2.onrender.com/movie/" + _id, { //radera baserat på id
            method: "DELETE", //radera
            headers: {
              "Accept": "application/json", //accepterar json
              "Content-type": "application/json" //skickar json
             }
          });
          const data = await res.json(); //sätter svaret till data

          this.getMovies(); //kör getmovies igen för att uppdatera listan
          
        } catch(error) { //vid error
          console.error(error)
        }
      }
  
  //slutar methods
  },

    mounted() { //lifecykle hook som körs näe en vue komponenet laddats in
      
      this.getMovies(); //körs getMovies
    }

  }

</script>

<template>
<div id="addMovie">
    <addMovie @movieAdded="getMovies()"/> <!--när film lagt till via addMovie komponenten kör GetMovies -->
  </div>

  
  <main>
    <div>
      <h1>Filmer</h1>
      <div id="divMovie">
        <!--Listar alla filmer via movie komponenten, gör detta genom varje film unika _id -->
    <movie @deleteMovie="deleteMovie(movie._id)" v-for="movie in allMovies" :movie="movie" :key="movie._id"/>
    </div>
    </div>

    
  </main>
  
  
  
</template>

<style scoped>

/*Styles*/ 
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

  #addMovie {
    z-index: -1;
    right: 0;
  }

  @media (min-width: 600px) {
  #divMovie {
    display: grid;
    grid-template-columns: repeat(2, 1fr); 
  }
}
}

</style>
