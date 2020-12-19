<template>
  <main id="app">
    <header>
      <h1>Game of Chance</h1>

    </header>
    <game/>
  </main>
</template>

<script>
import Game from './components/Game.vue'

export default {
  name: 'App',
  components: {
    Game,
  },
 
  methods : {

  }
}
</script>

<style>
body {
  margin: 0
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  display: flex;
  flex-direction: column;
  background-color: cornflowerblue;
  height: 100%;
  min-height: 100vh;
  padding: 0;
}
</style>
