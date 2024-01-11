<script setup>
import { ref } from 'vue';

const arrow = ref('<-');

function left() {
  arrow.value = '<-';
}

function right() {
  arrow.value = '->';
}

</script>


<template>
  <div id="arrows">
    <p @click.left="left" @click.right="right">
     {{ arrow }}
    </p>
  </div>
</template>

<style scoped>
#arrows {
  font-size: 50px;
}
</style>
