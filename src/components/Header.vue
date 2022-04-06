<template>
<!-- emit @click="$emit('search', searchFilm)" -->
    <header class="bg-dark d-flex align-items-center">
        <div class="container">
            <div class="row text-white">
                <div class="col-12">
                    <nav class="navbar d-flex justify-content-between">
                        <div class="my-container-img">
                            <img class="h-100" src="@/assets/img/netflix.png" alt="">
                        </div>
                        <div>
                            <input @keyup.enter="$emit('search', searchFilm)" v-model.trim="searchFilm" class="me-2 py-1 border border-primary bg-dark text-white" placeholder="Search">
                            <button @click="deleteSearch()" class="btn btn-outline-danger">Search</button>
                        </div>
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
        .my-container-img{
            width: 50%;
            height: 15vh;
        }
    }
</style>