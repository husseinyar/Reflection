<template>
  
   <h1>Welcome Reflection Game</h1>
  <button class="button1" @click="Start" :disabled="isplaying">play</button>
  <Block v-if="isplaying==true" :delay="delay" @end="gameOver" />
  <Results v-if='showResulets' :score="score"/>
</template>
v-if='showResulets'

<script>
import Block from './components/Block.vue'
import Results from './components/Results.vue'

export default {
  name: 'App',
  components: { Block, Results},
   data(){
    return{
    isplaying: false,
    delay:null,
    score: null,
    showResulets:false

    }
   },
  methods:{
   Start(){
     
     this.delay= 2000 + Math.random()* 5000
     this.isplaying = true
      this.showResulets= false
   },
   gameOver(clicktime){
   this.score = clicktime
   this.isplaying= false
    this.showResulets= true
    
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
.button1{
  background-color: #4c63af; /* Green */
  border: none;
  color: white;
  padding: 15px 32px;
  text-align: center;
  text-decoration: none;
  display: inline-block;
  font-size: 16px;
  margin: 4px 2px;
  cursor: pointer;
}

</style>
