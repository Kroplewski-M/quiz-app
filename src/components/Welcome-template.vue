<template>
<div class="h-[40px]"></div>
  <div class="w-[600px] h-[300px] bg-purple-400 mx-auto rounded-md drop-shadow-lg text-center">
        <p class="pt-16 text-[30px] font-bold">Welcome to the online quiz</p>
        <p class="pt-5 text-gray-700">Its an easy comp-sci quiz</p>
        <button @click.prevent="startQuiz()" class="mt-[35px] w-[120px] h-[40px] bg-green-600 rounded-md active:mt-[37px]">Start now</button>
  </div>
</template>

<script>
export default {
    emits:['start',],
    data(){
        return{
           start: false,
        }
    },
    methods:{
        startQuiz(){
            this.start = true;
            if(this.start){
            console.log(this.start);
             this.$emit('start',this.start);
            }
        }
    }
}
</script>

<style>

</style>