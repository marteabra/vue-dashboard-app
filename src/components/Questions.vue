<template>
   <div id="questionApp">

   </div>
</template>

<script>
export default {
   name: 'questionApp',
   components: {

   },
   data(){
      questions:	[
    {
      text:	"What is 20-12?",
      responses: [
        {text: "5", letter: "A"},
        {text: "8", letter: "B"},
        {text: "-2", letter: "C"},
        {text: "1", letter: "D"}
      ],
      answer: 'B',
      correct: "That is correct.",
      incorrect: "That is wrong."
    },{
      text:	"What is the capital of Australia?",
      responses: [
        {text: "Victora", letter: "A"},
        {text: "Sidney", letter: "B"},
        {text: "Melbourne", letter: "C"},
        {text: "Carberra", letter: "D"}
      ],
      answer: 'D',
      correct: "That is correct.",
      incorrect: "That is wrong."
    },{
      text:	"Who is Emily Dickinson",
      responses: [
        {text: "Poeth", letter: "A"},
        {text: "Author", letter: "B"},
        {text: "Singer", letter: "C"},
        {text: "Actor", letter: "D"}
      ],
      answer: 'A',
      correct: "That is correct.",
      incorrect: "That is wrong."
    },{
      text:	"Who inventet CSS?",
      responses: [
        {text: "Tim Berners-Lee", letter: "A"},
        {text: "Brendan Eich", letter: "B"},
        {text: "Håkon Wium Lie", letter: "C"},
        {text: "Jack Korby", letter: "D"}
      ],
      answer: 'C',
      correct: "That is correct.",
      incorrect: "That is wrong."
    }
  ]
   }
}
</script>

<style>

</style>