<template>
  <div>
    <h3>Coin Game</h3>
    <bet-input/>
  </div>

</template>

<script>
import BetInput from './BetInput.vue'
export default {
  components: { BetInput },
  name: "CoinGame",
  data () {
    return {
      betSet : false
    }
  }
}
</script>

<style>

</style>