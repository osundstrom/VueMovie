<script>
    export default {
        name: "addMovie",
    data() {
        return {
            grade: 0
        };
    },
    methods: {
        updateGrade(x) {
            this.grade = x.target.value; 
        }
    }
};
</script>

<template>
    <div id="allContent">
   <p>
  <button class="btn btn-primary" type="button" data-bs-toggle="collapse" data-bs-target="#collapseWidthExample" aria-expanded="false" aria-controls="collapseWidthExample">
    <i class="fa-solid fa-plus fa-sm"></i>
  </button>
</p>
<div style="min-height: 120px;">
  <div class="collapse collapse-horizontal" id="collapseWidthExample">
    <div class="card card-body" style="max-width: 80vw;">
        <form>
        <label for="Inputname" class="form-label">Film titel</label>
        <input type="text" class="form-control" id="Inputname" aria-describedby="name of movie">
        <label for="customRange3" class="form-label">Betyg: {{ grade }}</label>
        <input type="range" class="form-range" min="0" max="10" step="1" id="customRange3" :value="grade"  @input="updateGrade">
        <label class="form-check-label" for="flexSwitchCheckDefault"> Sett filmern:</label>
        <input class="form-check-input" type="checkbox" role="switch" id="flexSwitchCheckDefault">
        <hr>
        <button type="button" class="btn btn-success btn-small">Lägg till</button>
    </form>
    </div>
  </div>
</div>

</div>


</template>

<style scoped>
.form-check-label{
    margin-right: 1vw;
}

#allContent {
    position: absolute;
    z-index: 1;
}

</style>
