<template>
    <div class="row">
        <h2>SERIES</h2>
        <div v-for="serie in series" :key="serie.id" class="col-3 p-1 m-2 border border-danger border-2 rounded-3">
          <p>Titolo: {{ serie.name }} </p>
          <p>Titolo Originale: {{ serie.original_name }} </p>
          <p>Lingua Originale: 
            <span class="fi fi-" :class="serie.original_language"></span> 
          </p>
          <p>Rating: {{ serie.vote_average }} </p>
        </div>
    </div>
</template>

<script>
export default {
    name: "seriesComponent",
    props: {
        series: Array,
    }
}
</script>

<style lang="scss" scoped>

</style>