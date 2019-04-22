<template>
  <div id="app">
    <h1>Would you rather...</h1>
    <WouldYouRatherQuestion
            v-for="question in questions"
            v-bind:key="question.id"
            v-bind:question="question.question"
            v-bind:answer1="question.answer1"
            v-bind:answer2="question.answer2"
            v-on:answer-changed="answerChanged">
    </WouldYouRatherQuestion>


    <WouldYouRatherAnswer
            v-bind:message="userSelectionMessage">
    </WouldYouRatherAnswer>
  </div>
</template>

<script>
import WouldYouRatherQuestion from './components/WouldYouRatherQuestion.vue'
import WouldYouRatherAnswer from './components/WouldYouRatherAnswer.vue'

export default {
  name: 'app',
  data() {
    return {
      userSelectionMessage:'',
      questions: [
        {
          id: 0,
          question: 'Live in a triangle shaped house or circle shaped house?',
          answer1: 'live in triangle house',
          answer2: 'Live in a circle house',
        },
        {
          id: 1,
          question: 'Be a wizard or a superhero?',
          answer1: 'Be a wizard',
          answer2: 'Be a superhero',
        },
        {
          id: 2,
          question: 'Have an elephant per or cat pet?',
          answer1: 'Have an elephant',
          answer2: 'Have a cat',
        }
      ]
    }
  },
  components: {
    WouldYouRatherQuestion,
    WouldYouRatherAnswer
  },
  methods: {
    answerChanged(answer) {
      this.userSelectionMessage = `Thanks! You selected ${answer}`
    }
  }
}

</script>

<style>

</style>
