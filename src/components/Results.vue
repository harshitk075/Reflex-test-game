<template>
  <h2>Your Reaction Time is {{score}}ms</h2>
  <h2>{{level}}</h2>
</template>

<script>
export default {
    props: ['score'],
    data(){
        return{
            level: null,
        }
    },

    mounted(){
        if(this.score<300){
            this.level= "Faster than a bullet"
        }
        else if(this.score<400){
            this.level= "Magic Fingers"
        }
        else{
            this.level= "Pick Up the Pace!"
        }
    }
}
</script>

<style>

</style>