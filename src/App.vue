<template>
<div class="w-[100vw] h-[100vh] bg-blue-500">
  <WelcomeTemplate @start="start()" v-if="welcome"></WelcomeTemplate>
  <div class=" mx-auto w-[400px] md:w-[700px] h-[auto] bg-blue-500 rounded-md text-center pt-10">
    <questionTemplate @question-answered="questionAnswered" :questions="questions" :questionsAnswered="questionsAnswered" v-if="questionsAnswered < amountofQuestions && welcome == false"></questionTemplate>
    <ResultsTemplate :correctAnswers="correctAnswers" v-else-if="questionsAnswered >= amountofQuestions && welcome == false"></ResultsTemplate>
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
import WelcomeTemplate from './components/Welcome-template.vue';



export default {
  name: 'App',
  components: {
    questionTemplate,
    ResultsTemplate,
    WelcomeTemplate,
},
  data(){
    return{
      questions: quiz,
      questionsAnswered: 0,
      amountofQuestions: 4,
      correctAnswers: 0,
      welcome : true,
    }
  },
  methods:{
    reset(){
      this.questionsAnswered = 0;
      this.correctAnswers = 0;
      this.welcome = true;
    },
    questionAnswered(isCorrect){
      if(isCorrect){
        this.correctAnswers++;
      }
      this.questionsAnswered++;
      console.log(this.correctAnswers);
    },
    start(){
        this.welcome = false;
      }
   },
}
</script>

<style>

</style>
