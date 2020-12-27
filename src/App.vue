<template>
  <h1>Reaction Timer Game</h1>
  <button @click="isplaying" :disabled='gamestarted'>Play</button>
  <block v-if="gamestarted" :delay='delay' @end='results' />
  <div>
    <res v-if='gamended' :score='score' />
  </div>
</template>

<script>
import block from './components/block.vue';
import res from './components/Results.vue'
export default {
  name: 'App',
  data(){
    return{
      gamestarted: false,
      delay: null,
      score: null,
      gamended: false,
    }
  },

  components: { block, res },

  methods:{
    isplaying(){
      this.gamestarted= true
      this.gamended=false
      this.delay= 1000+ Math.random()*5000
    },
    results(rtime){
      this.score= rtime
      this.gamended= true
      this.gamestarted=false
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
