<template>
    <div>
        <main v-if="movies.length !== 0 " class="d-flex flex-wrap justify-content-center py-4">
            <Film
            v-for="(element, index) in movies"
            :key="index"
            :title="element.title"
            :name="element.name"
            :originalTitle="element.original_title"
            :originalName="element.original_name"
            :language="element.original_language"
            :vote="element.vote_average"
            :urlImage="element.poster_path"
            :overview="element.overview"
            />
        </main>
        <div v-else class="my-main d-flex justify-content-center align-items-center flex-column">
            <h1 class="pt-5 text-white">NESSUN TITOLO CERCATO O TROVATO</h1>
            <p class="text-secondary fs-4">Prova a cercare un nuovo film</p>
        </div>
        
    </div>
</template>

<script>
import Film from './Film.vue';

export default {
    name: "IndexMain",
    props: ['movies'],
    components: {
    Film,
    },
    data: function(){
        return{
        }
    },
    methods:{
    }
}
</script>

<style>
    main{
        background-color: #2e3a46;
    }
    .my-main{
        height: 85vh;
        background-color: #2e3a46;
    }
</style>