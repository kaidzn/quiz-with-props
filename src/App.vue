<template>
    <TopContent />
    <QuizQuestion :question="currentQuestion" />
    <UnderQuestion :totalQuestions="questions.length" :currentIndex="currentIndex" @next="nextQuestion" @previous="previousQuestion" />
</template>

<script>
import TopContent from './components/TopContent.vue';
import QuizQuestion from './components/QuizQuestion.vue';
import UnderQuestion from './components/UnderQuestion.vue';

export default {
  name: 'App',
  components: {
    TopContent,
    QuizQuestion,
    UnderQuestion
  },
  data() {
    return {
      questions: [
        {
          title: 'Question 1',
          options: [
            { id: 'q1_option1', text: 'Option 1' },
            { id: 'q1_option2', text: 'Option 2' },
            { id: 'q1_option3', text: 'Option 3' }
          ],
          correctAnswer: 'Option 1'
        },
        {
          title: 'Question 2',
          options: [
            { id: 'q2_option1', text: 'Option 1' },
            { id: 'q2_option2', text: 'Option 2' },
            { id: 'q2_option3', text: 'Option 3' }
          ],
          correctAnswer: 'Option 2'
        }
      ],
      currentIndex: 0
    };
  },
  computed: {
    currentQuestion() {
      return this.questions[this.currentIndex];
    }
  },
  methods: {
    nextQuestion() {
      if (this.currentIndex < this.questions.length - 1) {
        this.currentIndex++;
      }
    },
    previousQuestion() {
      if (this.currentIndex > 0) {
        this.currentIndex--;
      }
    }
  }
}
</script>

<style>

</style>
