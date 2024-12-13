<script>
    export default {
        name: "movie",
        props:  {
            movie: Object
        }
    }

</script>

<template>


    <div class="card" style="width: 18rem;">
    <div class="card-body">
    <h5 class="card-title">{{movie.name}} <a :href="`https://www.imdb.com/find/?q=${movie.name}`" ><i class="fa-solid fa-arrow-up-right-from-square fa-2xs"></i></a></h5>
    <p class="card-text">Betyg: {{movie.ratingImdb}} </p>
    <p class="card-text">Sett den: {{movie.watched ? "Ja" : "Nej"}} </p>
    <button @click="$emit(`deleteMovie`)" type="button" class="btn btn-danger"><i class="fa-regular fa-trash-can fa-sm"></i></button>
    <!--<button type="button" class="btn btn-warning"><i class="fa-regular fa-pen-to-square fa-sm"></i></button>-->
  </div>
</div>


</template>

<style scoped>


.card{ 
    
    border: 1px solid black;
    max-width: 90vw;
    margin-bottom: 1vh;
    margin-right: 1vw;
    border-radius: 10px;
    padding: 0% 1vw 0% 1vw;
   
    font-size: 100%;
    
    h2{
       
        white-space: nowrap;
    }

    button{
        margin-right: 1vw;
    }
}
</style>
