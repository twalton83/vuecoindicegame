<template>
  <div>
  <h2> 
    Coins: {{coins}} 
  </h2>
  <h3 v-if="gameName">{{gameName}} Game</h3>

  <div v-if="gameSelected === false">
    <!-- this "passes down the method" similarly to react -->
    <game-selector @set-game="setGame"/>
  </div>

  <div v-if="gameName === 'Coin'">
    <coin-game :viewable="betSubmitted" 
    @playerChoice="setPlayerChoice"
     />
      <bet-input v-on:set-bet="setBet" v-if="!betSubmitted && gameSelected"/>
  </div>

  <div v-else-if="gameName === 'Dice'">
    <dice-game :viewable="betSubmitted" 
     @playerChoice="setPlayerChoice"/>
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
      coins: 100,
      answer: null,
      playerSelection: null
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
      this.coins = this.coins - bet
      this.betSubmitted = true
      this.answer = this.randomSelection()
    },
    randomSelection(){
      if (this.gameName === 'Coin'){
        return Math.floor(Math.random() * 2) + 1
      } else {
        return Math.floor(Math.random() * 6) + 1
      }
    },
    setPlayerChoice (choice){
      console.log(choice)
      this.playerSelection = choice
    },
    checkForWin(){
      return this.playerSelection === this.answer ? this.coins = this.coins + this.bet * 2 : null

    }
  }
}
</script>

<style>

</style>