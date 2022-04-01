<template>
  <div id="app">
    <!-- 32882ac1b7e4c41041b47646c6d0f4cd -->
    <Header/>
    <Main/>

  </div>
</template>

<script>
import Header from './components/Header.vue'
import Main from './components/Main.vue'


export default {
  name: 'App',
  components: {
    Header,
    Main
  }
}
</script>

<style lang="scss">
@import 'src/assets/style.scss';
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
}
</style>
