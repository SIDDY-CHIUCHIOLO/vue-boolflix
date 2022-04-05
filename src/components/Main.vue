<template>
    <div>
        <main v-if="movies" class="d-flex flex-wrap justify-content-center py-4">
            <div v-for="(element, index) in movies" :key="index+'movies'">
            </div>
            <Film
            v-for="(element, index) in movies"
            :key="index"
            :title="element.title"
            :name="element.name"
            :originalTitle="element.original_title"
            :originalName="element.original_name"
            :language="element.original_language"
            :vote="element.vote_count"
            :urlImage="element.poster_path"
            />
        </main>
        <div v-else class="my-main text-center">
            <h1 class="pt-5 text-white">NESSUN TITOLO CERCATO</h1>
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