<template>
    <p>
        Voto: {{ rating }}
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