<script>

//import
import movie from '../components/movie.vue'

//export
export default {
    components: {movie}
  }

</script>

<template>


 <!--Inehåll på sidna-->
  <main>
    <div>
    <h1>Film!</h1>
    <p>Vem gillar inte att titta på en bra film eller serie?</p>
    <p>Jag gillar att kolla på film och serier i alla fall och alla har vi våra favoriter. 
    Därav skapade jag en sida där man kan recensera filmer lite enkelt. (borde byggas på för att bli bättre så som text för att skriva åsikter, namn på den som lämnat recension osv). </p>
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
    text-decoration: underline;
  }
}


</style>
