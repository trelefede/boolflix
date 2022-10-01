<template>
    <p>
        Voto: 
        <font-awesome-icon icon="fa-solid fa-star" v-for="fullStar in this.fullStars" :key="fullStar" class="star" />
        <font-awesome-icon icon="fa-regular fa-star" v-for="emptyStar in this.emptyStars" :key="emptyStar" />
    </p>
</template>

<script>
export default {
    name: "ratingComponent",
    data(){
        return{
            fullStars: this.getArrayFullStars(),
            emptyStars: this.getArrayEmptyStars()
        }
    },
    props: {
        rating: Number 
    },
    methods:{
        getArrayFullStars(){
            const array = [];
            const rating = Math.ceil(this.rating / 2);
            for(let i = 0; i < rating; i++){
                array.push(i);
            }
            return array;
        },
        getArrayEmptyStars(){
            const array = [];
            const rating = ( 10 - (Math.ceil(this.rating / 2)));
            for(let i = 5; i < rating; i++){
                array.push(i);
            }
            return array;
        }
    },
}
</script>

<style lang="scss" scoped>
.star{
    color: #fb0;
}

</style>