<template>
    <img class="img-fluid" :src="`${this.posterBaseLink}${this.posterSize}${this.posterApiLink}`" :alt="this.alt">
</template>

<script>
export default {
    name: "posterComponent",
    data(){
        return{
            posterBaseLink: 'https://image.tmdb.org/t/p/',
            posterSize: 'w342',
        }
    },
    props:{
        posterApiLink: String,
        alt: String
    }
}
</script>

<style lang="scss" scoped>
    
</style>