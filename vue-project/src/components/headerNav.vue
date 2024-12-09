
<!--Script KOD-->
<script>
  export default {
    name: "headerNav",
    components: {
      RouterLink
    }
  }

  import { RouterLink } from 'vue-router';

</script>



<!--HTML KOD-->
<template>


  <div id="allContent">
  <div id="divHead">
  <div class="dropdown">

  <button class="dropdown btn btn-dark" type="button" data-bs-toggle="dropdown" aria-expanded="false">
    &#9776;
  </button>
  <ul class="dropdown-menu">
    <li><RouterLink class="dropdown-item" to="/">Hem</RouterLink></li>
    <li><RouterLink class="dropdown-item" to="/movie">Filmer</RouterLink></li>
    <li><RouterLink class="dropdown-item" to="/vue">Vue</RouterLink></li>
    
  </ul>
</div>
</div>
</div>


</template>



<!--CSS KOD-->
<style scoped>
  
    

    button{
      background-color: none  ;
      font-weight: 900;
      font-size: x-large;
      margin-top: 2vh;
      margin-left: 2vw;
      background:none;
      color: white;
      z-index: 1;

    }

    ul{
      z-index: 1;
    }
   
    #divHead{
      background-image: url(../assets/greyAudience.jpg);
      background-size: cover;
      background-position: center;
      height: 18vw;
      width: 100vw;
      position: relative;
      top: 0;
    left: 0;
    border-bottom: 1px solid black;
    z-index: 0;
    
    
    
    }
</style>
