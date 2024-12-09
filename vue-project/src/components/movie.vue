<script>
    export default {
        name: "movie",
        props:  {
            movie: Object
        }
    }

</script>

<template>
    <article>
        <h2>{{movie.name}}</h2>
        <p>Betyg: {{movie.ratingImdb}} </p>
        <p>Sett den: {{movie.watched ? "Ja" : "Nej"}} </p>
    </article>

</template>

<style scoped>
article{
    background-color: white;
    border: 1px solid black;
    max-width: 90vw;
    margin-bottom: 1vh;
    background-color: lightgoldenrodyellow;
}
</style>
