<template>
  <div class="block" v-if="showblock" @click="stopTimer">click here{{ delay }}</div>
</template>

<script>
export default {
  props:['delay'],
  data(){
    return{
      showblock:false,
      scoreResult:0,
      timer:null   
    }
  },
  mounted(){
    setTimeout(() => {
      this.showblock=true;
      this.startTimer()
    },this.delay);
  },
  methods:{
    startTimer(){
        this.timer=setInterval(()=>{
          this.scoreResult+=50;
        },100)
    },
    stopTimer(){
      clearInterval(this.timer);
      console.log(this.scoreResult);
    }
  }
  
}
</script>

<style>
  .block{
    background-color: blueviolet;
    width: 400px;
    height: 200px;
    margin: 20px auto;
    padding-top: 30px;
  }
</style>