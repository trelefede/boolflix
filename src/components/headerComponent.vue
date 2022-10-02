<template>
    <header>
        <input type="text" 
            v-model="query" 
            @keyup="search" 
            placeholder="Cerca...">
    </header>
</template>

<script>
export default {
    name: "headerComponent",
    data(){
        return {
            query: ''
        }
    },
    methods: {
        search(){
            this.$emit('search', this.query);
        }
    }
}
</script>

<style lang="scss" scoped>

</style>