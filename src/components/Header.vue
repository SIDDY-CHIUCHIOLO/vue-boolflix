<template>
<!-- emit @click="$emit('search', searchFilm)" -->
    <header class="bg-dark d-flex align-items-center">
        <div class="container">
            <div class="row text-white">
                <div class="col-12">
                    <nav class="navbar d-flex justify-content-end">
                        <input @keyup="$emit('search', searchFilm)" v-model="searchFilm" class="me-2 py-1 border border-primary bg-dark text-white" placeholder="Search">
                        <button @click="deleteSearch()" class="btn btn-outline-danger">Search</button>
                    </nav>
                </div>
            </div>
        </div>
    </header>
</template>

<script>
export default {
    name: "IndexHeader",
    data: function(){
        return{
            searchFilm: "",
        }
    },
    methods:{
        deleteSearch(){
            this.searchFilm = ""
        }
    }
}
</script>

<style lang="scss" scoped>
    header{
        height: 15vh;
    }
</style>