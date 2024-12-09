<script>
  export default {
    name: "Footer.vue"
  }

</script>

<template>

    <footer>
        <p>Skapad av <a href="mailto:ossu2300@student.miun.se">Oskar Sundström</a></p>
    </footer>


</template>

<style scoped>
    footer{
        text-align: center;
        width: 100vw;
        position: fixed;
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
