<template>
    <div>
      <input type= "number" v-model = "bet"/> 
      <button   v-on:click="$emit('submit-bet', 'bet')">
        Submit
      </button>
    </div>
</template>

<script>
export default {
  name : 'BetInput',
  props : ['coins'],
  data () {
    return {
      bet : null
    }
  }
}
</script>

<style>

</style>