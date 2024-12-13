<script>

    //exports
    export default {
        name: "addMovie",
    data() {
        return { 
            imdbRating: 0, //betyg för att slider ska vara 0
            movie: { //en film
                name: "", //namn
                ratingImdb: 0, //betyg
                watched: false, //tittad

            },
            
                
            
        };
    },
    emits:["movieAdded"], //event när en film läggs till
    methods: {
        updateGrade(x) { //Håller kolla på värdet för slidern i formuläret
            this.ratingImdb = x.target.value; 
        },
        async addMovie(){ //funktion för att lägga till film
            try {
                

                    let movieBody = this.movie
                    //console.log(movieBody)

                    //Hätar api med en post förfrågan
                    const res = await fetch("https://koamoment2.onrender.com/movie", {
                        method:"POST", //post
                        headers: {
                                "Accept": "application/json", //JSON
                                "Content-type": "application/json" //JSON
                                },
                        body: JSON.stringify(movieBody) //skcikas som JSON
                        })

                    const data = await res.json(); //Svar från förfrågan
                    //console.log(data)

                    //sätter tillbaka standardvärden
                    this.movie.ratingImdb = 0;
                    this.movie.name = "";
                    this.movie.watched = false;
                    
                    //emit för att visa att filmen lagts till
                    this.$emit("movieAdded")

                    
                    }

            
            catch(error) { //vid error
                console.error(error)
            }}
        
        }
};
</script>
<!---->
<template>
    <div id="allContent">
   <p>
    <!--Knapp för att visa formulär allt via bootstrap-->
  <button id="btnfirst"class="btn btn-primary" type="button" data-bs-toggle="collapse" data-bs-target="#collapseWidthExample" aria-expanded="false" aria-controls="collapseWidthExample">
    <i class="fa-solid fa-plus fa-sm"></i>
  </button>
</p>
<div id="Divcol" style="min-height: 120px;">
  <div class="collapse collapse-horizontal" id="collapseWidthExample">
    <div class="card card-body" style="max-width: 80vw;">

        <!-- Formulär som visas när man öppnat via knappen, slider för betyyg, text för namn och boolen för sett eller inte-->

        <form @submit.prevent="addMovie">  <!-- Förhindrar standard och kör addMovie -->
        <label for="Inputname" class="form-label">Film titel</label>
        <input type="text" class="form-control" id="Inputname" aria-describedby="name of movie" v-model="movie.name" required>
        <label for="customRange3" class="form-label">Betyg: {{ movie.ratingImdb }}</label> <!-- Uppdaterar betyg ovanför slidern när man ändrar värde -->
        <input type="range" class="form-range" min="0" max="10" step="1" id="customRange3" v-model="movie.ratingImdb" >
        <label class="form-check-label" for="flexSwitchCheckDefault"> Sett filmern:</label>
        <input class="form-check-input" type="checkbox" role="switch" id="flexSwitchCheckDefault" v-model="movie.watched">
        <hr>
        <button type="submit" class="btn btn-success btn-small" >Lägg till</button>
    </form>
    </div>
  </div>
</div>

</div>


</template>


<style scoped>
/*Styles*/
.form-check-label{
    margin-right: 1vw;
    z-index: 1;
}
#Divcol {
    z-index: 1;
}
.collapse{
    z-index: 1;
}
#btnfirst{
    z-index: -1;
}
p{
    z-index: -1;
}

#allContent {
    position: absolute;
    left: 2vw;
    margin-top: 2vh;
    z-index: 1;
}

</style>
