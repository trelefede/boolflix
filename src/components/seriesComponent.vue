<template>
    <div class="row">
        <h2>SERIES</h2>
        <div v-for="serie in series" :key="serie.id" class="col-3 p-1 m-2 border border-danger border-2 rounded-3">
          <p>Titolo: {{ serie.name }} </p>
          <p>Titolo Originale: {{ serie.original_name }} </p>
          <flagComponent :languages="series.original_language" />
          <p>Rating: {{ serie.vote_average }} </p>
        </div>
    </div>
</template>

<script>
import flagComponent from "@/components/flagComponent.vue"

export default {
    name: "seriesComponent",
    props: {
        series: Array,
    },
    components: {
      flagComponent,
    }
}
</script>

<style lang="scss" scoped>

</style>