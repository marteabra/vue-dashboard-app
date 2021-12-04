<template>
   <h4>{{ index + 1}}
      <span v-html="text">
       </span>
    </h4>
     <ol v-for="response in responses">
        <li><input type="radio" @click="checkAnswer(response.letter)" />
        <span v-html="response.text"> 
        </span>
        </li>
     </ol>
     <div v-if="questionAnswered">
        <div v-if="questionIsCorrect" v-html="correct">
        </div>
        <div v-else v-html="incorrect">
        </div>
      </div>
</template>

<script>
import Questions from './Questions.vue';

export default {
   props: {
      index: { type: Number, required: true },
		text: { type: String, required: true },
		responses: { type:[String, String], required: true },
		answer: { type: String, required: true },
		correct: { type: String, required: true },
		incorrect: { type: String, required: true }

   },
   data: function(){
      questionAnswered: false;
      questionIsCorrect: false;
   },
   methods: {
      checkAnswer: function(selectedAnswer){
         if(selectedAnswer === this.answer)
         {
            this.questionIsCorrect = true;
         }else{
            this.questionIsCorrect = false;
         }
         questionAnswered = true;
      }
   }
   
}
</script>

<style>

</style>