<template>
  <div id="app">
    <Header
    @search="searchFilmsEndSeries"
    />
    <Main
      :movies = moviesAndSeries
    />
  </div>
</template>

<script>
import axios from 'axios';
import Header from './components/Header.vue'
import Main from './components/Main.vue'
import '@fortawesome/fontawesome-free/css/all.css'
import '@fortawesome/fontawesome-free/js/all.js'


export default {
  name: 'App',
  components: {
    Header,
    Main
  },
  data: function(){
      return{
        listSearchFilm: null,
        movies:[],
        series:[],
        moviesAndSeries: [],
        apiUrl: 'https://api.themoviedb.org/3/search/',
        apiKey: '?api_key=e99307154c6dfb0b4750f6603256716d&query=',
        movieSearch: '',
      }
  },
  methods:{
    searchFilmsEndSeries(searchText){
      if(searchText != ''){
        this.movieSearch = searchText;
        this.getMovies();
        this.getSeries();
      } else{
        this.moviesAndSeries = '',
        console.warn('NESSUN TITOLO CERCATO')
      }
    },
    getMovies(){
      axios
      .get(this.apiUrl + 'movie'+ this.apiKey + this.movieSearch)
      .then((response) =>{
        console.log(response.data.results);
        this.movies = response.data.results;
        this.moviesAndSeries = [...this.movies, ...this.series];
      })
      .catch((error) =>{
        console.log(error)
      })
    },
    getSeries(){
      axios
      .get(this.apiUrl + 'tv'+ this.apiKey +this.movieSearch)
      .then((response) =>{
        console.log(response.data.results);
        this.series = response.data.results;
        this.moviesAndSeries = [...this.movies, ...this.series];
      })
      .catch((error) =>{
        console.log(error)
      })
    }
  }
}
</script>

<style lang="scss">
@import 'src/assets/style.scss';
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
}
</style>
