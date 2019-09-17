<template>
  <div>
    <div v-if="currentQuestion !== null" class="question">
      <FillTheGap v-if="currentQuestion.type === 'ftg'" :question="currentQuestion" ref="currentQuestionElement" />
      <MultipleChoice v-else-if="currentQuestion.type === 'mc'" :question="currentQuestion" ref="currentQuestionElement" />
    </div>
    <div v-else>
      Congratulations! You finished all the questions.
    </div>

    <div class="check-bar" v-if="currentQuestion !== null">
      <button class="check-button" @click="checkAnswer()">
        CHECK
      </button>
    </div>
  </div>
</template>

<script>
  import questionsJson from '../questions.json'
  import FillTheGap from './FillTheGap'
  import MultipleChoice from './MultipleChoice'

  export default {
    name: 'Questions',
    components: {
      FillTheGap,
      MultipleChoice
    },
    data () {
      return {
        questions: questionsJson,
        currentQuestionId: 0
      }
    }, 
    computed: {
      currentQuestion () {
        return this.currentQuestionId >= this.questions.length ? null : this.questions[this.currentQuestionId];
      }
    },
    methods: {    
      checkAnswer() {
        if (this.$refs.currentQuestionElement.checkAnswer() === true)
          alert('Correct!');
        else
          alert('Incorrect :(');

        this.currentQuestionId++;
      }
    }
}
</script>

<style scoped>
  .question {
    margin-top: 20%;
  }

  .check-bar {
    position: fixed;
    bottom: 0px;
    padding: 20px;
    background: white;
    width: 100%;
  }
  
  .check-button {
    padding: 5px 10px;
    letter-spacing: 2px;
    border-radius: 5px;
    background-color: #c9dbd0;
    box-shadow: none;
    font-size: 20px;
    font-family: Courier;
  }
  
  .check-button:focus {
    outline: none;
  }
</style>
