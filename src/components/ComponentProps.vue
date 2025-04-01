/**
* Author: Davi Bacalhau (littlesekii)
* Purpose: Understand and use Vue 3 props.
*
**/

<script setup>

const props = defineProps([
    "name",
    "age"
]);

</script>

<template>
	<div class="container">
		<h2>{{ name }}, {{ age }} years old.</h2>

	</div>
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
