<template>
  <div>
    <game v-bind:coins="coins"/>
  </div>
</template>

<script>
import Game from './Game.vue'
export default {
  name: 'GameContainer',
  components: {
    Game
  },
  props : ['coins']
}
</script>

<style>

</style>