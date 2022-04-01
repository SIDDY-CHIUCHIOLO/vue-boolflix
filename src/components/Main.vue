<template>
    <main>
        <div>
            <button @click="getApiFilms()" class="btn bg-white">clicca</button>
        </div>
    </main>
</template>

<script>
import axios from 'axios';
export default {
    name: "IndexMain",
    data: function(){
        return{
            listApiFilms: null,
        }
    },
    methods:{
        getApiFilms(){
            axios
            .get('https://api.themoviedb.org/3/movie/550?api_key=32882ac1b7e4c41041b47646c6d0f4cd')
            .then((result) =>{
                console.log( result);
            })
        }
    }
}
</script>

<style>
    main{
        height: 85vh;
        background-color: #2e3a46;
    }
</style>