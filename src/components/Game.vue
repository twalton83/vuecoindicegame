<template>
  <div>
  <h1 v-if="gameName">{{gameName}} Game</h1>
      <h2> 
        Coins: {{coins}} 
      </h2>
  <div v-if="gameSelected === false">
    <!-- this "passes down the method" siilarly to react -->
    <game-selector v-on:set-game="setGame"/>
 
  </div>

  <div v-if="gameName === 'Coin'">
    <coin-game/>
      <bet-input v-on:set-bet="setBet" v-if="!betSubmitted && gameSelected"/>
  </div>

  <div v-else-if="gameName === 'Dice'">
    <dice-game/>
       <bet-input v-on:set-bet="setBet" v-if="!betSubmitted && gameSelected"/>
  </div>



  </div>
</template>

<script>
import BetInput from './BetInput.vue';
import CoinGame from './CoinGame.vue'
import DiceGame from './DiceGame.vue';
import GameSelector from './GameSelector.vue';
export default {
  components: {
    CoinGame,
    DiceGame,
    GameSelector,
    BetInput
 },
  data () {
    return  {
      gameName : "",
      gameSelected: false,
      betSubmitted: false,
      coins: 100
    }
  },
  methods : {
    setGame (gameName) {
      const game = gameName;
      this.gameName = `${game}`
      this.gameSelected = true
    },
    setBet (amount) {
      const bet = amount;
      alert(bet)
      this.coins = this.coins - bet
      this.betSubmitted = true
    }
  }
}
</script>

<style>

</style>