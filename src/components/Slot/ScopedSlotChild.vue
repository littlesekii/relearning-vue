/**
* Author: Davi Bacalhau (littlesekii)
* Purpose: Understand and use Vue 3 scoped slot.
*
**/

<script setup>
const props = defineProps(['students']);
</script>

<template>
	<slot v-for="student, index in props.students" :student="student" :index="index"></slot>
</template>

<style scoped>
.container {
	padding: 20px;
	display: flex;
	flex-direction: column;

	justify-content: center;
	align-items: center;

	border: 1px solid var(--black-light);
}
</style>
