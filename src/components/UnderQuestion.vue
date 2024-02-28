<template>
  <div class="under-question">
    <button @click="previousQuestion" :disabled="currentIndex === 0">Previous Question</button>
    <button @click="nextQuestion" :disabled="currentIndex === totalQuestions - 1">Next Question</button>
  </div>
</template>

<script>
export default {
  name: 'UnderQuestion',
  props: {
    totalQuestions: {
      type: Number,
      required: true
    },
    currentIndex: {
      type: Number,
      required: true
    }
  },
  methods: {
    nextQuestion() {
      this.$emit('next');
    },
    previousQuestion() {
      this.$emit('previous');
    }
  }
}
</script>

<style scoped>
.under-question {
  margin-top: 20px;
}
button {
  font-size: 16px;
  padding: 8px 16px;
  margin-right: 10px;
  cursor: pointer;
}
button:disabled {
  opacity: 0.5;
  cursor: not-allowed;
}
</style>
