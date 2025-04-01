/**
* Author: Davi Bacalhau (littlesekii)
* Purpose: Understand and use Vue 3 scoped slot.
*
**/

<script setup>
import { reactive } from 'vue';
import ScopedSlotChild from './ScopedSlotChild.vue';

const students = reactive(
  [
    {
      name: "Davi Bacalhau",
      term: 1 
    },
    {
      name: "Flávia Helena",
      term: 1 
    },
    {
      name: "João Vitor",
      term: 2 
    },
    {
      name: "Igor Santiago",
      term: 3 
    },
    {
      name: "Pedro Ornandes",
      term: 2
    },
  ]
);
</script>

<template>
  <div class="container">

    <!-- # means v-slot so #="data" is the same as v-slot="data" -->
    <ScopedSlotChild :students="students" #="data" >
      
      <div class="student">
        {{ data.index + 1 }} - {{ data.student.name }} ({{ data.student.term }}st term)</div>
    </ScopedSlotChild>

  </div>
</template>

<style scoped>
  .container {
	padding: 20px;
	display: flex;
	flex-direction: column;

	justify-content: center;
	/* align-items: center; */

	border: 1px solid var(--black-light);
}
.student {
  padding-bottom: 5px;
}
</style>
