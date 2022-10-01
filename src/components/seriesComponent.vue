<template>
    <div class="row">
        <h2>SERIES</h2>
        <div v-for="serie in series" :key="serie.id" class="col-3 p-1 g-3 border border-danger border-2 rounded-3">
          <posterComponent :posterApiLink="serie.poster_path" :alt="serie.original_title" />
          <p>Titolo: {{ serie.name }} </p>
          <p>Titolo Originale: {{ serie.original_name }} </p>
          <flagComponent :languages="serie.original_language" />
          <ratingComponent :rating="serie.vote_average" />
        </div>
    </div>
</template>

<script>
import flagComponent from "@/components/flagComponent.vue"
import posterComponent from "@/components/posterComponent.vue"
import ratingComponent from "@/components/ratingComponent.vue"

export default {
    name: "seriesComponent",
    props: {
        series: Array,
    },
    components: {
      flagComponent,
      posterComponent,
      ratingComponent
    }
}
</script>

<style lang="scss" scoped>

</style>