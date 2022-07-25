<template>
<div class="w-[100vw] h-[100vh] bg-blue-500">
  <div class=" mx-auto w-[700px] h-[auto] bg-blue-500 rounded-md text-center pt-10">
    <questionTemplate v-if="questionsAnswered < amountofQuestions"></questionTemplate>
    <ResultsTemplate v-else></ResultsTemplate>
 </div>
 <div class="mx-auto w-[100px]">
  <button class="w-[100px] h-[40px] bg-red-400 font-semibold mt-[30px] active:mt-[33px]">Reset</button>
</div>
</div>
</template>

<script>
import '../public/index.css';
import questionTemplate from './components/Questions-template.vue';
import quiz from '../questions.json';
import ResultsTemplate from './components/results-template.vue';



export default {
  name: 'App',
  components: {
    questionTemplate,
    ResultsTemplate,
},
  data(){
    return{
      questions: [],
      questionsAnswered: 4,
      amountofQuestions: 4,
      correctAnswers: 0,
    }
  },
  methods:{
   },
  mounted(){
   this.questions = quiz;
  // console.log(this.questions.question[0]);
   console.log(this.questions.questions[0].question);
  },

}
</script>

<style>

</style>
