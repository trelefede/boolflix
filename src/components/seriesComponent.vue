<template>
    <div class="row">
        <h2 class="text-center dark fs-1 mt-4">SERIES</h2>
        <div v-for="serie in series" :key="serie.id" class="col-3 p-1 g-3">
          <div class="card bg-dark text-white">
            <posterComponent :posterApiLink="serie.poster_path" :alt="serie.original_title" class="card-img" />
            <div class="movie card-img-overlay d-none">
              <p>Titolo: {{ serie.name }} </p>
              <p>Titolo Originale: {{ serie.original_name }} </p>
              <flagComponent :languages="serie.original_language" />
              <ratingComponent :rating="serie.vote_average" />
            </div>
          </div>
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