<template>
  <div class="quiz-container">
    <div class="quiz">
      <h1 class="quiz-title">Quiz</h1>
      <div class="question-box">
        <div v-if="idx < count">
          <p class="question">
            {{ questions[idx]["question"] }}
          </p>
          <label
            v-for="(answer, index) in questions[idx].answers"
            :key="index"
            :for="index"
            :class="
              (index == questions[idx].correctAnswer && selectedAnswer != '',
              selectedAnswer == index)
            "
          >
            <input
              :id="index"
              type="checkbox"
              class="hidden"
              :value="index"
              @change="answered($event)"
              :disabled="selectedAnswer != ''"
            />
            {{ answer }}
          </label>
          <button
            class="next"
            @click="nextQuestion"
            v-show="selectedAnswer != '' && idx < count - 1"
          >
            Next &gt;
          </button>
          <button
            class="finish"
            @click="showResults"
            v-show="selectedAnswer != '' && idx == count - 1"
          >
            Finish
          </button>
        </div>
        <div v-else>
          <h2>Results</h2>
          <p>
            Correct Answers: <span>{{ correctAnswers }}</span>
          </p>
          <p>
            Wrong Answers: <span>{{ wrongAnswers }}</span>
          </p>
          <div class="play-again">
            <button @click="resetQuiz">Play again</button>
          </div>
        </div>
      </div>
      <!--</div>-->
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      idx: 0,
      selectedAnswer: "",
      correctAnswers: 0,
      wrongAnswers: 0,
      count: 5,
      questions: [
        {
          question: "Which country hosted the FIFA Women’s World Cup in 2015?",
          answers: { a: "USA", b: "Canada", c: "China", d: "France" },
          correctAnswer: "b",
        },
        {
          question:
            "Native to the Caribbean, what sort of animal is the mountain chicken?",
          answers: { a: "Bird", b: "Cat", c: "Fish", d: "Frog" },
          correctAnswer: "d",
        },
        {
          question: "Is Java and JavaScript the same?",
          answers: { a: "True", b: "False" },
          correctAnswer: "b",
        },
        {
          question: "What is the capital of Australia??",
          answers: { a: "Carberra", b: "Melbourne", c: "Sidney", d: "Dubbo" },
          correctAnswer: "a",
        },
        {
          question: "Who inventet CSS?",
          answers: {
            a: "Tim Berners-Lee",
            b: "Brendan Eich",
            c: "Bjarne Jacobsen",
            d: "Håkon Wium Lie",
          },
          correctAnswer: "d",
        },
      ],
    };
  },
  methods: {
    answered(e) {
      this.selectedAnswer = e.target.value;
      if (this.selectedAnswer == this.questions[this.idx].correctAnswer) {
        this.correctAnswers++;
      } else {
        this.wrongAnswers++;
      }
    },
    nextQuestion() {
      this.idx++;
      this.selectedAnswer = "";
      document.querySelectorAll("input").forEach((el) => (el.checked = false));
    },
    showResults() {
      this.idx++;
    },
    resetQuiz() {
      this.idx = 0;
      this.selectedAnswer = "";
      this.correctAnswers = 0;
      this.wrongAnswers = 0;
    },
  },
};
</script>

<style>
.quiz-container {
  position: relative;
  width: 30vw;
  padding: 1em;
}

.quiz {
  position: absolute;
  height: 44vh;
  width: 90%;
  background: lightgray;
}

.quiz-title {
  text-align: center;
  margin: 5% 5%;
}

.question-box {
  padding: 10px;
  margin: 5px;
  background: white;
}

.question {
  padding: 10px;
  margin: 5px;
}

label {
  padding: 4px;
  margin: 3px;
  text-align: center;
}

label:hover {
  color: aquamarine;
}

.next {
  position: relative;
  margin: 3px;
  padding: auto;
}
</style>