<script setup>

import { defineProps, defineEmits } from 'vue';

const props = defineProps({
  idx: Number,
  text: String,
  difficulty: Number
})

const emit = defineEmits(['change'])

function inputChanged(e) {
  const newDifficulty = e.target.value;
  emit('change', [props.idx - 1, newDifficulty]);
}

</script>


<template>
  <div :id="idx" class="Qstn">
    <p>
      <b><i>№{{ idx }}:</i></b> {{ text }}
    </p>
    <p>
      <b><i>Difficulty:</i></b>
      <input type="text" :value="difficulty" @change="inputChanged">
    </p>
  </div>
</template>


<style scoped>
.Qstn {
  font-family: Helvetica;
  background-color: #bddeff;
  color: black;
  border: 5px solid #ffdebd;
  margin-top: 5px;
  margin-bottom: 5px;
  margin-left: 20%;
  margin-right: 20%;
  border-radius: 1px;
}
</style>


