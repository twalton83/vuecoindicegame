<template>
  <div>
    <h3>Dice Game</h3>
    <bet-input v-bind:max = "coins" />
  </div>
</template>

<script>
import BetInput from './BetInput.vue'
export default {
  components: { 
    BetInput 
  },
  name: "DiceGame",
  props : ['coins']

}
</script>

<style>

</style>