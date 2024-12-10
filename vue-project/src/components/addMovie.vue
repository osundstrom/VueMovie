<script>

    export default {
        name: "addMovie",
    data() {
        return {
            imdbRating: 0,
            movie: {
                name: "",
                ratingImdb: 0,
                watched: false,

            },
            
                
            
        };
    },
    emits:["movieAdded"],
    methods: {
        updateGrade(x) {
            this.ratingImdb = x.target.value; 
        },
        async addMovie(){
            try {
                

                    let movieBody = this.movie
                    console.log(movieBody)

                    const res = await fetch("https://koamoment2.onrender.com/movie", {
                        method:"POST",
                        headers: {
                                "Accept": "application/json",
                                "Content-type": "application/json"
                                },
                        body: JSON.stringify(movieBody)
                        })

                    const data = await res.json();
                    console.log(data)

                    
                    this.movie.ratingImdb = 0;
                    this.movie.name = "";
                    this.movie.watched = false;

                    this.$emit("movieAdded")

                    
                    }

            
            catch(error) {
                console.error(error)
            }}
        
        }
};
</script>

<template>
    <div id="allContent">
   <p>
  <button id="btnfirst"class="btn btn-primary" type="button" data-bs-toggle="collapse" data-bs-target="#collapseWidthExample" aria-expanded="false" aria-controls="collapseWidthExample">
    <i class="fa-solid fa-plus fa-sm"></i>
  </button>
</p>
<div style="min-height: 120px;">
  <div class="collapse collapse-horizontal" id="collapseWidthExample">
    <div class="card card-body" style="max-width: 80vw;">
        <form @submit.prevent="addMovie">
        <label for="Inputname" class="form-label">Film titel</label>
        <input type="text" class="form-control" id="Inputname" aria-describedby="name of movie" v-model="movie.name" required>
        <label for="customRange3" class="form-label">Betyg: {{ movie.ratingImdb }}</label>
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
.form-check-label{
    margin-right: 1vw;
    z-index: 1;
}

.collapse{
    z-index: 1;
}
#btnfirst{
    z-index: -1;
}

#allContent {
    position: absolute;
    left: 10vw;
    margin-top: 2vh;
    
}

</style>
