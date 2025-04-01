/**
* Author: Davi Bacalhau (littlesekii)
* Purpose: Understand and use Vue 3 emit.
*
**/

<script setup>

const emit = defineEmits([
  "reset"
]);

function resetParentCount() {
  emit("reset");
}

</script>

<template>
  <!-- Using this type of emit with "$" results in a warning -->
  <button @click="$emit('add')">Add 1</button>
	<button @click="$emit('add-amount', 5)">Add 5</button>

  <!-- Using defineEmits is the recommended way to do this-->
  <button @click="emit('reset')">Reset</button>

  <!-- <button @click="resetParentCount">Reset</button> -->
</template>

<style scoped>
  button {
    width: 70px;
    padding: 5px;
    margin-bottom: 5px;
  }
  button:last-of-type {
    margin: 0;
  }
</style>
