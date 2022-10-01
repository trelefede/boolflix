<template>
    <div class="row">
        <h2>FILM</h2>
        <div v-for="movie in movies" :key="movie.id" class="col-3 p-1 m-2 border border-danger border-2 rounded-3">
          <p>Titolo: {{ movie.title }} </p>
          <p>Titolo Originale: {{ movie.original_title }} </p>
          <p>Lingua Originale: 
            <span class="fi fi-" :class="movie.original_language"></span> 
          </p>
          <p>Rating: {{ movie.vote_average }} </p>
        </div>
    </div>
</template>

<script>
export default {
    name: "moviesComponent",
    props: {
        movies: Array,
    }
}
</script>

<style lang="scss" scoped>

</style>