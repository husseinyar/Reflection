<template>
 <p>reaction time: {{score}}</p>
 <p class="renk">{{renk}}</p>
</template>

<script>
export default {
props:['score'],
data(){

  return{

    renk:null
  }
}, 
mounted(){

  if(this.score<250){

    this.renk="Ninja fingers"
   }else if (this.score <400) {
    this.renk= "Rapid Reflexes"
  } else {
     this.renk= "Snail pace..."
  }
}
  
}

</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style>
.renk{

  font-size: 1.4em;
  color: blue;
  font-weight: bold;
}

</style>
