<template>
    <div class="row">
        <h2>FILM</h2>
        <div v-for="movie in movies" :key="movie.id" class="col-3 p-1 m-2 border border-danger border-2 rounded-3">
          <p>Titolo: {{ movie.title }} </p>
          <p>Titolo Originale: {{ movie.original_title }} </p>
          <flagComponent :languages="movie.original_language" />
          <p>Rating: {{ movie.vote_average }} </p>
        </div>
    </div>
</template>

<script>
import flagComponent from "@/components/flagComponent.vue"

export default {
    name: "moviesComponent",
    props: {
        movies: Array,
    },
    components: {
      flagComponent,
    }
}
</script>

<style lang="scss" scoped>

</style>