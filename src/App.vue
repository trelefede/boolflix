<template>
  <div id="app">
    <div>
      <input type="text" v-model="query" @keyup="search" placeholder="Cerca...">
    </div>
    <main class="container-xl">
      <moviesComponent :movies="movies" />
      <seriesComponent :series="series" />
    </main>
  </div>
</template>

<script>
import axios from "axios";
import { apiKey } from "@/env.js";

import moviesComponent from "@/components/moviesComponent.vue"
import seriesComponent from "@/components/seriesComponent.vue"

export default {
  name: 'App',
  data(){
    return {
      apiUrl: 'https://api.themoviedb.org/3/search/',
      movies: [],
      series: [],
      query: ''
    }
  },
  methods: {
    search(){
      this.queryApi(this.query);
    },
    queryApi(textToSearch){ 
        // axios call to API movies
        axios.get(`${this.apiUrl}movie?api_key=${apiKey}&query=${textToSearch}`)
          .then((response)=>{
            this.getMovies(response);
          })
          .catch((error)=>{
            console.log(error.message);
          })
        // axios call to API series
        axios.get(`${this.apiUrl}tv?api_key=${apiKey}&query=${textToSearch}`)
          .then((response)=>{
            this.getSeries(response);
          })
          .catch((error)=>{
            console.log(error.message);
          })
    },
    getMovies(response){
      if (response.status === 200){
        this.movies = response.data.results;
        console.log('movies', this.movies);
      }
    },
    getSeries(response){
      if (response.status === 200){
        this.series = response.data.results;
        console.log('series', this.series);
      }
    },
  },
  components: {
    moviesComponent,
    seriesComponent
  }
}
</script>

<style lang="scss">
@import "~bootstrap/scss/bootstrap";
@import "/node_modules/flag-icons/css/flag-icons.min.css";


</style>
