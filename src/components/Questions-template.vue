<template>
    <div class="absolute w-[100%] max-w-[700px] h-[70px] bg-red-400 rounded-md"></div>
    <p class="z-50 relative text-[20px] pt-[20px] font-bold font-mono">1 out of 4 questions answered</p>
    <div class="w-[100%] h-[100px] bg-green-500 border-b-2 border-black border-solid ">
      <p class="pt-[47px]">{{questions.questions[this.index].question}}</p>
    </div>
      <div class="w-[100%] h-[100%] bg-gray-200 rounded-b-md">
      <div>
        <h1 class="answer">{{questions.questions[this.index].answers[0].text}}</h1>
        <h1 class="answer">{{questions.questions[this.index].answers[1].text}}</h1>
        <h1 class="answer">{{questions.questions[this.index].answers[2].text}}</h1>
        <h1 class="answer rounded-b-md">{{questions.questions[this.index].answers[3].text}}</h1>
      </div>
    </div>
</template>

<script>
export default {
  props: ['questions','questionsAnswered'],
  data(){
    return{
      index : this.questionsAnswered,
    } 
  },
  methods:{

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
}
.answer:hover{
  border: solid 3px green;
  transform: scale(1.1);
  background-color: white;

}</style>

