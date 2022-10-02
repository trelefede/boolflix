<template>
    <div class="row m-4">
        <h2 class="dark fs-1 my-4">FILM</h2>
        <div v-for="movie in movies" :key="movie.id" class="col-2 p-1 my-1">
          <div class="ft-height card bg-dark text-white">
            <posterComponent :posterApiLink="movie.poster_path" :alt="movie.original_title" class="card-img flex-grow-1 " />
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
.ft-height{
  height: 100%;
}
</style>