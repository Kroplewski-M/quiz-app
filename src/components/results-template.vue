<template>
  <div class="w-[400px] md:w-[100%] h-[230px] md:h-[200px] bg-purple-400 rounded-md border-2 border-solid border-gray-100">
    <p class="text-[50px] font-bold text-gray-50 md:pt-10 drop-shadow-xl">You got {{this.correctAnswers}} out of 4 Correct!</p>
    <p class="pt-[25px] font-semibold">{{getResponse()}}</p>
  </div>
</template>

<script>
export default {
  props:['correctAnswers',],

data(){
  return{
    response:"",
  }
},
methods:{
  getResponse(){
    if(this.correctAnswers <= 2){
      this.response = "You need to study harder!"
      return this.response;
    }
    else{
      this.response = "Congrats you know some stuff!"
      return this.response;
    }
  }
}
}
</script>

<style>


</style>