/**
* Author: Davi Bacalhau (littlesekii)
* Purpose: Understand and use Vue 3 emit.
*
**/

<script setup>
import { ref } from 'vue';
import EmitChild from './EmitChild.vue';

const count = ref(0);

function add() {
	count.value++;
}

function addAmount(amount) {
	count.value += amount;
}

function reset() {
	count.value = 0;
}

</script>

<template>
	<div class="container">
		<div>{{ count }}</div>
		<br/>
		<EmitChild 
			@add="add" 
			@add-amount="(amount) => count += amount" 
			@reset="reset" 
		/>
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
