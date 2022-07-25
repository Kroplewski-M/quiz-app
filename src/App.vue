<template>
  <questionTemplate></questionTemplate>
<div class="w-[100vw] h-[100vh] bg-blue-500">
  <div class=" mx-auto w-[700px] h-[auto] bg-blue-500 rounded-md text-center pt-10">
    <div class="absolute w-[100%] max-w-[700px] h-[70px] bg-red-400 rounded-md"></div>
    <p class="z-50 relative text-[20px] pt-[20px] font-bold font-mono">1 out of 4 questions answered</p>
    <div class="w-[100%] h-[100px] bg-green-500 border-b-2 border-black">
      <p class="pt-[47px] ">Sample question 1</p>
    </div>
    <div class="w-[100%] h-[100%] bg-gray-200 rounded-b-md">
      <div>
        <h1 class="answer">Sample Answer 1</h1>
        <h1 class="answer">Sample Answer 2</h1>
        <h1 class="answer">Sample Answer 3</h1>
        <h1 class="answer rounded-b-md">Sample Answer 4</h1>
      </div>
    </div>
  </div>
</div>
</template>

<script>
import '../public/index.css';
import questionTemplate from './components/Questions-template.vue';
import quiz from '../questions.json';


export default {
  name: 'App',
  components: {
    questionTemplate,
  },
  data(){
    return{
      questions: [],
    }
  },
  methods:{
   },
  mounted(){
   this.questions =quiz;
   console.log(this.questions);
  }

}
</script>

<style>
.answer{
  width: 100%;
  height: 70px;
  border: solid 2px black;
  border-top: 0px;
  padding-top: 20px;
  font-weight:300;
}
</style>
