<template>
  <div id="app">
    <follow-me></follow-me>
  </div>
</template>

<script>
import FollowMe from './components/FollowMe.vue'

export default {
  name: 'App',
  components: {
    FollowMe
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
