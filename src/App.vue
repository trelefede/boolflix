<template>
  <div id="app">
    <div>
      <input type="text" v-model="query"> <button @click="search">Cerca</button>
    </div>
    <div class="container">
      <div class="row">
        <div v-for="movie in movies" :key="movie.id" class="col-3 p-1 m-2 border border-danger border-2 rounded-3">
          <p>Titolo: {{ movie.title }} </p>
          <p>Titolo Originale: {{ movie.original_title }} </p>
          <p>Lingua Originale: {{ movie.original_language }} </p>
          <p>Rating: {{ movie.vote_average }} </p>
      </div>
      </div>
    </div>
  </div>
</template>

<script>
import axios from "axios";
import { apiKey } from "@/env.js";

export default {
  name: 'App',
  data(){
    return {
      movies: [],
      query: ''
    }
  },
  methods: {
    search(){
      this.queryApi(this.query);
    },
    queryApi(textToSearch){ 
        axios.get(`https://api.themoviedb.org/3/search/movie?api_key=${apiKey}&query=${textToSearch}`)
        .then((response)=>{
          console.log(response)
          if (response.status === 200){
            this.movies = response.data.results;
            console.log(this.movies);
          }
        })
        .catch((error)=>{
          console.log(error.message);
        })
    },
  },
  components: {
    
  }
}
</script>

<style lang="scss">
@import "~bootstrap/scss/bootstrap";

</style>
