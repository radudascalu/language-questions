<template>
  <div>
      {{ questionParts[0] }}
      <input type="text" v-model="userAnswer" />
      {{ questionParts[1] }}
  </div>
</template>

<script>
  export default {
    name: 'FillTheGap',
    props: ['question'],
    data() {
        return {
            questionParts: this.question.text.split('_'),
            userAnswer: ''
        }
    },
    methods: {
        checkAnswer() {
            return this.userAnswer === this.question.correctAnswer;
        }
    }
}
</script>

<style scoped>
    input {
        text-align: center;
        font-family: Courier;
        font-size: 20px;
        width: 100px;
    }
</style>
