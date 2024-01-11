<script setup>
import { ref } from 'vue';

let color = ref('red');

function changeColor(newColor) {
  color.value = newColor;
}

</script>


<template>
  <div id="colors">
    <!--
    <p @click="changeColor('red')">Red</p>
    <p @click="changeColor('green')">Green</p>
    <p @click="changeColor('blue')">Blue</p>
    -->
    <div id="clrDiv" @click="changeColor('red')">Red</div>
    <div id="clrDiv" @click="changeColor('green')">Green</div>
    <div id="clrDiv" @click="changeColor('blue')">Blue</div>
  </div>
</template>

<style scoped>
#colors {
  margin-top: 10px;
  margin-bottom: 10px;
  margin-left: 20%;
  margin-right: 20%;
  background-color: v-bind(color);
}

#clrDiv {
  border: 3px solid black;
  color: white;
  margin: 5px;
}
</style>
