<template>
 <h1>how fast can you catch me game</h1>
 <button @click="start" :disabled="isplaying">play</button>
<div v-if="isplaying">
 <BlockBlue :delay="delay"/>
</div>
</template>

<script>
import BlockBlue from "./components/BlockBlue.vue"
export default {
  name: 'App',
  components: {
  BlockBlue
  },
  data(){
      return{
         isplaying:false,
         delay:null
      }
  },
  methods:{
    start(){
        this.isplaying=true;//play buttom function
        this.delay=(2000+Math.random()*5000);//timer in blockblue
        
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
