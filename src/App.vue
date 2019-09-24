<template>
  <div>
    <!-- <HelloWorld msg="Welcome to Your Vue.js App"/> -->
    <SubredditExplorer/>
  </div>
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'
// import GoogleLayout from './components/GoogleLayout.vue'
import SubredditExplorer from './components/SubredditExplorer.vue'

export default {
  name: 'app',
  components: {
    SubredditExplorer
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
