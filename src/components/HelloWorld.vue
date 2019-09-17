<template>
  <div>
    {{ questions }}
  </div>
</template>

<script>
  import questionsJson from '../questions.json'
  
  export default {
    name: 'HelloWorld',
    data () {
      return {
        questions: questionsJson
      }
    }
}
</script>

<style scoped>
</style>
