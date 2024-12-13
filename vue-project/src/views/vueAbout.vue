<script>

import movie from '../components/movie.vue' //importerar

export default { //exporterar
    components: { movie}
  }

</script>

<template>


  <!--Innehåll-->
<main>
    <div>
      <h1>Vue</h1>  
      <p>Jag tycker Vue är smidigt att arbea med. Det jag har att jämföra med är egentligen Angular vilket jag tycker är snarlikt särskilt därför både använder sig av komponenter.
        Vue känns dock lite lättare att kommaigång med om man jämför med hur jag minns Angular. 
        Det som känns bättre i Vue är att det känns mer flexibelt, det går lättare att styra funktioner troligen för det ej är ett Fullstack-ramverk som Angular. 
      </p>
      <p>Det jag upplevt som svårast är att veta hur jag ska dela in i vilka komponenter, detta var inte ett överdrivet stort projekt så vissa indelningar kändes onödiga att göra i flera komponenter. 
        Sedan var jag även lite seg på att förstå hur man skulle göra med v-model för att kunna uppdatera datan korrekt i min slider.  </p>
    </div>
  </main>
  
  
</template>

<style scoped>

/* styles*/ 
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
