<template>
  <h2 class='out'>Your Reaction Time is: <span id='sp'>{{score}} </span> ms</h2>
  <h1 class='out'>{{level}}</h1>
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
.out{
    font-size: 2.3em;
    color: slategrey;
    font-weight: bold;
}
#sp{
    color: rgb(33, 21, 202);;
    text-decoration: underline;
}
</style>