<template>
  <div>
    <!-- events are emitted by children for parents to listen to- this works similarly to passing down a method as a prop in React -->
    <button 
    v-on:click = "$emit('set-game', 'Coin')"
    value="coin">
      Coin
    </button>
    <button 
    v-on:click = "$emit('set-game', 'Dice')"
    value = "dice">
      Dice
    </button>
  </div>
</template>

<script>
export default {
  name: "GameSelector"
}
</script>

<style>

</style>