<template>
    <header class="d-flex justify-content-between align-items-center position-fixed top-0 px-4 bg-dark">
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
    height: 70px;
    z-index: 9999;
    width: 100%;
}

img{
    width: 15%;
}
</style>