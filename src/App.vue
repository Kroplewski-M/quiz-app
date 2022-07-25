<template>
<div class="w-[100vw] h-[100vh] bg-blue-500">
  <div class=" mx-auto w-[700px] h-[auto] bg-blue-500 rounded-md text-center pt-10">
    <questionTemplate></questionTemplate>
    <AnswersTemplate></AnswersTemplate>
 </div>
</div>
</template>

<script>
import '../public/index.css';
import questionTemplate from './components/Questions-template.vue';
import answersTemplate from './components/Answers-template.vue'
import quiz from '../questions.json';
import AnswersTemplate from './components/Answers-template.vue';


export default {
  name: 'App',
  components: {
    questionTemplate,
    answersTemplate,
    AnswersTemplate
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

</style>
