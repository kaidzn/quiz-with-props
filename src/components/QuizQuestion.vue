<template>
  <div class="quiz-question">
    <h2>{{ question.title }}</h2>
    <div v-for="(option, index) in question.options" :key="index">
      <input type="radio" :id="option.id" :value="option.text" v-model="selectedOption">
      <label :for="option.id">{{ option.text }}</label>
    </div>
  </div>
</template>

<script>
export default {
  name: 'QuizQuestion',
  props: {
    question: {
      type: Object,
      required: true
    }
  },
  data() {
    return {
      selectedOption: null
    };
  }
}
</script>

<style scoped>
.quiz-question {
  margin-bottom: 20px;
}
h2 {
  font-size: 20px;
  margin-bottom: 10px;
}
input[type="radio"] {
  margin-right: 5px;
}
label {
  font-size: 16px;
}
</style>
