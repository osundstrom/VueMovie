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
        <p>{{movie.ImdbRating}} </p>
        <p>{{movie.watched}} </p>
    </article>

</template>

<style scoped>
article{
    background-color: white;
    border: 1px solid black;
    max-width: 90vw;
}
</style>
