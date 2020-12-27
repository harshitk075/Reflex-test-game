<template>
  <h1 id='st'>Reaction Timer Game</h1>
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
  margin-top: 60px;
}
#st{
  color: rgb(33, 21, 202);
  font-size: 5em;
}

button{
  background: rgb(54, 226, 39);
  color: white;
  border: none;
  padding: 8px 16px;
  border-radius: 4px;
  font-size: 16px;
  letter-spacing: 1px;
  cursor: pointer;
  margin: 10px;
}

button[disabled]{
  opacity: 0.2;
  cursor: not-allowed;
}
</style>
