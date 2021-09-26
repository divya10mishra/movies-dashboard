<template>
  <MoviesList msg="Movies-List"/>
</template>

<script>
import MoviesList from './components/MoviesList.vue'


export default {
  name: 'App',
  components: {
    MoviesList
  }
  
}
</script>

<style>
#app {
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
