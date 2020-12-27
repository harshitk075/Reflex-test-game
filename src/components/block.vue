<template>
   <div class="block" v-if='showblock' @click="stoptimer">
       CLICK HERE FAST!!!
   </div>
</template>

<script>
export default {
    props: ['delay'],
    data(){
        return{
            showblock: false,
            timer: null,
            reactionTime: 0,
        }
    },

    mounted(){
        setTimeout(()=>{
            this.showblock= true
            this.starttimer()
        },this.delay)
    },

    methods:{
        starttimer(){
            this.timer= setInterval(()=>{
                this.reactionTime+=10
            },10)
        },
        stoptimer(){
            clearInterval(this.timer)
            console.log(this.reactionTime)
            this.$emit('end',this.reactionTime)
        }
    }
}
</script>

<style>
.block{
    width: 400px;
    background: #0faf87;
    color: white;
    text-align: center;
    padding: 100px 0;
    margin: 40px auto;
    border-radius: 30px;
}
</style>