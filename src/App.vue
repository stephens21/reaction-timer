<script>
import Block from './components/Block.vue'
import Result from './components/Results.vue'

export default{
  name:'App',
  components:{Block, Result},
  data(){
    return{
      isPlaying: false,
      delay:null,
      score:null,
      showResults: false
    }

  },
  methods:{
    start(){
      this.delay = 2000 + Math.random() * 5000
      this.isPlaying = true
      this.score = true
      this.showResults = false
    },
    endGame(value){
      this.score = value
      this.isPlaying = false
      this.showResults = true
    }
  }
}

</script>

<template>
 <h1>Ninja Reaction Timer</h1>
 <button @click="start" :disabled="isPlaying">play</button>
 <Block v-if="isPlaying" :delay="delay" @end="endGame"/>
 <Result v-if="showResults" :score="score"/>

</template>

<style>
body{
  font-family: 'Gill Sans', 'Gill Sans MT', Calibri, 'Trebuchet MS', sans-serif;
  background: white;
  color: black;
  text-align: center;
  display: block;
}

#app{
  display: inline;
  color: #444;
}
button{
  background: #0faf87;
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
