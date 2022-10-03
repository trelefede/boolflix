<template>
    <div class="row m-4">
        <h2 class="dark fs-1 my-4">SERIES</h2>
        <div v-for="serie in series" :key="serie.id" class="col-3 p-1 g-3 my-2">
          <div class="ft-height card bg-dark text-white">
            <posterComponent :posterApiLink="serie.poster_path" :alt="serie.original_title" class="card-img flex-grow-1 " />
            <div class="serie card-img-overlay">
              <p>Titolo: {{ serie.name }} </p>
              <p>Titolo Originale: {{ serie.original_name }} </p>
              <flagComponent :languages="serie.original_language" />
              <ratingComponent :rating="serie.vote_average" />
              <p>Overview: {{ serie.overview }} </p>
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
.ft-height{
  height: 100%;
}

.serie{
  display: none;
}

.card:hover .serie{
  background-color: rgba(0, 0, 0, 0.441);
  display: inline-block;
  overflow-y: auto;
}
</style>