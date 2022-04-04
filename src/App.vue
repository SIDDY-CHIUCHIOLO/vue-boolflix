<template>
  <div id="app">
    <!-- 32882ac1b7e4c41041b47646c6d0f4cd-->

    <Header
    @search="getApiFilms"
    />
    <Main
      :listOfFilms = listSearchFilm
    />
  </div>
</template>

<script>
import axios from 'axios';
import Header from './components/Header.vue'
import Main from './components/Main.vue'


export default {
  name: 'App',
  components: {
    Header,
    Main
  },
  data: function(){
      return{
        listSearchFilm: null,
      }
  },
  methods:{
    getApiFilms(searchText){
      if(searchText != ''){
        axios
        .get('https://api.themoviedb.org/3/search/movie?api_key=e99307154c6dfb0b4750f6603256716d&query=' + searchText)
        .then((result) =>{
            this.listSearchFilm = result.data.results
            console.log(this.listSearchFilm)
        })
      } else{
        this.listSearchFilm = '',
        console.warn('NESSUN TITOLO CERCATO')
      }
    },
  }
}
</script>

<style lang="scss">
@import 'src/assets/style.scss';
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
}
</style>
