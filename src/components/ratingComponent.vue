<template>
    <p>
        Voto: {{ rating }} 
        <font-awesome-icon icon="fa-solid fa-star" />
        <font-awesome-icon icon="fa-regular fa-star" />
    </p>
</template>

<script>
export default {
    name: "ratingComponent",
    props: {
        rating: String 
    }
}
</script>

<style lang="scss" scoped>

</style>