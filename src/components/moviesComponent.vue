<template>
    <div class="row">
        <h2 class="text-center dark fs-1 mt-4">FILM</h2>
        <div v-for="movie in movies" :key="movie.id" class="col-3 p-1 g-3">
          <div class="card bg-dark text-white">
            <posterComponent :posterApiLink="movie.poster_path" :alt="movie.original_title" class="card-img" />
            <div class="movie card-img-overlay d-none">
              <p>Titolo: {{ movie.title }} </p>
              <p>Titolo Originale: {{ movie.original_title }} </p>
              <flagComponent :languages="movie.original_language" />
              <ratingComponent :rating="movie.vote_average" />
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
    name: "moviesComponent",
    props: {
        movies: Array,
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