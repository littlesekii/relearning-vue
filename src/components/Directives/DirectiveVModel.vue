/**
* Author: Davi Bacalhau (littlesekii)
* Purpose: Understand and use Vue 3 v-model directive.
*
**/

<script setup>
import { ref } from 'vue';

const label = ref("Not a model label");
const labelModel = ref("Model label")

function updateLabel(event) {
	label.value = event.target.value;
}

</script>

<template>
	<main>
		<div class="container">
			<p>{{ label }}</p>

			<!-- this input updates label by using a function -->
			<input type="text" @keyup="updateLabel" :value="label">
		</div>

		<div class="container">
			<p>{{ labelModel }}</p>

			<!-- this input updates label by using v-model directive -->
			<input type="text" v-model="labelModel">
		</div>
	</main>
</template>

<style scoped>
main {
	display: flex;
	flex-direction: column;
}

.container {
	margin: 10px;
	padding: 20px;
	display: flex;
	flex-direction: column;

	justify-content: center;
	align-items: center;

	border: 1px solid var(--black-light);
}

.container p {
	margin-bottom: 10px;
}

.container input {
	padding: 5px;
}
</style>
