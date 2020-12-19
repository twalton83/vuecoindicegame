<template>
  <div >
    <button v-if="viewable" @click.stop= "$emit('player-choice', '1')">
      Heads
    </button>
    <button v-if="viewable"
    @click.stop= "$emit('player-choice', '2')">
      Tails
    </button>
  </div>
</template>

<script>

export default {
  name: "CoinGame",
  data () {
    return {
    }
  },
  methods: {

   
  },
  props : ["viewable"]
}
</script>

<style>

</style>