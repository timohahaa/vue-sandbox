<script setup>
import { questions } from './store/question'
import Question from './components/Question.vue';
import Color from './components/Colors.vue'
import Arrows from './components/Arrows.vue'
import { ref } from 'vue';

const qstns = ref(questions);

function updateDifficulty(data) {
  const [idx, newDifficulty] = data;
  qstns.value[idx].difficulty = newDifficulty;
  qstns.value.sort((a, b) => {
    if (a.difficulty < b.difficulty) {
      return -1;
    }
    if (a.difficulty > b.difficulty) {
      return 1;
    }
    return 0;
  });
  qstns.value.reverse();
}

</script>

<template>
  <p>Welcome! ;)</p>
  <Color />
  <Arrows />
  <div v-for="(q, idx) in qstns">
    <Question @change="updateDifficulty" :idx="idx + 1" :text="q.text" :difficulty="q.difficulty" />
  </div>
</template>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
