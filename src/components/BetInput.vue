<template>
    <div>
      <input type= "number" v-model = "bet"/> 
      <button  v-on:click= "$emit('set-bet', '10')">
        Submit
      </button>
    </div>
</template>

<script>
export default {
  name : 'BetInput',
  data () {
    return {
      bet : null
    }
  }
}
</script>

<style>

</style>