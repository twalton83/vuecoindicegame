<template>
  <div>
  <h1>{{gameName}}</h1>
  <div v-if="gameSelected === false">
    <!-- this "passes down the method" siilarly to react -->
    <game-selector v-on:set-game="setGame"/>
  </div>
  <div v-if="gameName === 'Coin'">
    <coin-game/>
  </div>
  <div v-else-if="gameName === 'Dice'">
    <dice-game/>
  </div>


  </div>
</template>

<script>
import CoinGame from './CoinGame.vue'
import DiceGame from './DiceGame.vue';
import GameSelector from './GameSelector.vue';
export default {
  components: {
    CoinGame,
    DiceGame,
    GameSelector
 },
  data () {
    return  {
      gameName : "",
      gameSelected: false
    }
  },
  methods : {
    setGame (gameName) {
      const game = gameName;
      this.gameName = `${game} Game`
      this.gameSelected = true
    }
  },
   props : ['coins']
}
</script>

<style>

</style>