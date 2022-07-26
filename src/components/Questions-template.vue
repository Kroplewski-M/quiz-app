<template>
  <div class="absolute w-[400px] md:w-[100%] max-w-[700px] h-[70px] bg-gray-200 rounded-md"></div>
    <div class="progress absolute w-[100%] max-w-[700px] h-[70px] bg-red-400 rounded-md z-50" :style="{width: `${getWidth()}%` }"></div>
    <p class="z-50 relative text-[20px] pt-[20px] font-bold font-mono">{{this.questionsAnswered}} out of 4 questions answered</p>
    <div class="w-[100%] h-[100px] bg-green-500 border-b-2 border-black border-solid ">
      <p class="pt-[47px]">{{questions.questions[this.questionsAnswered].question}}</p>
    </div>
      <div class="w-[100%] h-[100%] bg-gray-200 rounded-b-md">
      <div v-for="(answer, index) in questions.questions[questionsAnswered].answers" :key="index">
        <!-- <h1 class="answer">{{questions.questions[this.questionsAnswered].answers[0].text}}</h1> -->
        <h1 class="answer" @click.prevent="selectAnswer(answer.is_correct)">{{answer.text}}</h1>
      </div>
    </div>
</template>

<script>
export default {
  props: ['questions','questionsAnswered'],
  emits:['question-answered',],
  data(){
    return{

    } 
  },
  methods:{
   selectAnswer(isCorrect){
      this.$emit('question-answered', isCorrect);
   },
   getWidth(){
      if(window.innerWidth > 1500){
        return (this.questionsAnswered / 10 * 100)
      }
      else
      return (this.questionsAnswered / 7 * 100)
   }
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
  transition: all .5s ease-in-out;
  box-shadow: 0 20px 25px -5px rgb(0 0 0 / 0.1), 0 8px 10px -6px rgb(0 0 0 / 0.1);
}
.answer:hover{
  border: solid 3px green;
  transform: scale(1.1);
  background-color: white;
  cursor: pointer;
}
.progress{
  transition: all 1.5s ease-in-out;
}

</style>

