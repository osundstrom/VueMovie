<script>
//export
  export default {
    name: "Footer.vue"
  }

</script>
<!--Inehåll-->
<template>

    <footer>
        <p>Skapad av <a href="mailto:ossu2300@student.miun.se">Oskar Sundström</a></p>
    </footer>


</template>

<style scoped>
/*styles*/ 
    footer{
        text-align: center;
        width: 100vw;
        position: relative;
        left: 0;
        bottom: 1%;
        a {
           color: blue;
           text-decoration: none;
        }
        a:hover {
            text-decoration: underline;
        }
    }
</style>
