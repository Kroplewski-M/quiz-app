<template>
    <div class="w-[100%] h-[100%] bg-gray-200 rounded-b-md">
      <div>
        <h1 class="answer">Sample Answer 1</h1>
        <h1 class="answer">Sample Answer 2</h1>
        <h1 class="answer">Sample Answer 3</h1>
        <h1 class="answer rounded-b-md">Sample Answer 4</h1>
      </div>
    </div>
</template>

<script>
export default {

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

}

</style>