<template>
   
</template>


<script>
export default {
data: {
    title: 'My Test App',
    quiz: quiz,
    slides: slides,
    questionIndex: 0,
    slideIndex: 0,
    quizCompleted: 0,
    questionCompleted: 0,
    userResponses: new Array(quiz.questions.length)
  },
  methods: {
    next: function(){
      this.questionIndex++;
      if(this.slideIndex === quiz.questions.length)
      {
        this.quizCompleted = 1;
      }else{
      	this.quizCompleted = 0;
      }
    },
    prev: function(){
      this.questionIndex--;
    },
    slideNext: function(){
      this.slideIndex++;
    },
    slidePrev: function(){
      this.slideIndex--;
    },
    checkAnswer: function(){
      this.questionCompleted = 1;
    }
  }   
}

</script>

<style>

</style>