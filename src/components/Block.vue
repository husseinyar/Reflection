<template>
  <div class="block" v-if="showBlock" @click="stopTimer">
    Click me
  </div>
  
</template>

<script>
export default {
  props:['delay'],

  data(){

    return{

     showBlock: false,
     timmer: null,
     reactionTime:false
    }
  },
  mounted(){

    console.log('component mounted')
    setTimeout(()=> {
      this.showBlock= true
      this.startTimer()
    }, this.delay)
  },

 methods:{
  startTimer(){
   this.timmer= setInterval(() => {
     this.reactionTime+=10
   }, 10);
  },

  stopTimer(){
  clearInterval(this.timmer)
  this.$emit('end', this.reactionTime)
  }

 }
  
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

.block {

width: 400px;
border-radius: 20px;
background: lightgreen;
text-align: center;
margin: 40px auto;
padding: 100px 0;

}

</style>
