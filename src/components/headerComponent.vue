<template>
    <header class="d-flex justify-content-between align-items-center px-4 bg-dark">
        <div class="logo">
            <img src="https://upload.wikimedia.org/wikipedia/commons/0/08/Netflix_2015_logo.svg" alt="logo">
        </div>
        <div class="search">
            <input type="text" 
                v-model="query" 
                @keyup="search" 
                placeholder="Cerca...">
        </div>
       
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
header{
    height: 50px;
}
img{
    width: 10%;
}
</style>