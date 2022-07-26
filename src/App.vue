<template>
<div class="w-[100vw] h-[100vh] bg-blue-500">
  <div class=" mx-auto w-[400px] md:w-[700px] h-[auto] bg-blue-500 rounded-md text-center pt-10">
    <questionTemplate @question-answered="questionAnswered" :questions="questions" :questionsAnswered="questionsAnswered"  v-if="questionsAnswered < amountofQuestions"></questionTemplate>
    <ResultsTemplate :correctAnswers="correctAnswers" v-else></ResultsTemplate>
 </div>
 <div class="mx-auto w-[100px]">
  <button v-if="questionsAnswered == amountofQuestions" @click="reset()" class="w-[100px] h-[40px] bg-red-400 font-semibold mt-[30px] active:mt-[33px]">Reset</button>
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
      questions: quiz,
      questionsAnswered: 0,
      amountofQuestions: 4,
      correctAnswers: 0,
    }
  },
  methods:{
    reset(){
      this.questionsAnswered = 0;
      this.correctAnswers = 0;
    },
    questionAnswered(isCorrect){
      if(isCorrect){
        this.correctAnswers++;
      }
      this.questionsAnswered++;
      console.log(this.correctAnswers);
    }
   },
}
</script>

<style>

</style>
