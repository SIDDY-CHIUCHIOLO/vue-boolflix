<template>
    <div>
        <main v-if="listOfFilms">
            <Film
            v-for="(element, index) in listOfFilms"
            :key="index"
            :title="element.title"
            :originalTitle="element.original_title"
            :language="element.original_language"
            :vote="element.vote_count"
            />
        </main>
        <div v-else class="my-main text-center">
            <h1 class="pt-5 text-white">NESSUN TITOLO CERCATO</h1>
        </div>
    </div>
</template>

<script>
import Film from './Film.vue'

export default {
    name: "IndexMain",
    props: ['listOfFilms'],
    components: {
    Film,
    },
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