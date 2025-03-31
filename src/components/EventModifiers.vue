/**
* Author: Davi Bacalhau (littlesekii)
* Purpose: Understand and use Vue 3 event modifiers.
*
**/

<script setup>
import { ref } from 'vue';

const label = ref("Sample text");
const labelModel = ref(label.value);

const linkHint = ref("This link sends to google.com, but its prevented to do so...");
const linkHintOnce = ref("This link sends to google.com, but its prevented once...");

function updateLabel() {
	label.value = labelModel.value;
}

function alertEasterEgg() {
	alert('you found an easteregg')
}

</script>

<template>
	<main @click="alertEasterEgg">

		<!-- the .stop means the click wont be propagating to main element, -->
		<div @click.stop class="container">
			<p>{{ label }}</p>
			<input 
				type="text" 
				v-model="labelModel" 
				@keyup.enter="updateLabel"
			>
			<span>Press enter to submit</span>
		</div>

		<!-- event modifiers can also be stacked like those exemples below -->
		<a 
			href="https://google.com/" 
			:title="linkHint" 
			@click.stop.prevent="
				labelModel = 'you can\'t';
				updateLabel();
			"
		>
			Google.com<span> (prevented)</span>
		</a>

		<a 
			href="https://google.com/" 
			:title="linkHintOnce" 
			@click.stop.prevent.once="
				labelModel = 'you can now!';
				updateLabel();
			"
		>
			Google.com<span> (prevented once)</span>
		</a>
	</main>
</template>

<style scoped>
main {
	display: flex;
	flex-direction: column;

	height: auto;
}

main a {
	color: cornflowerblue;
	margin-top: 5px;
	align-self: flex-start;
}

main a span {
	text-decoration: underline;
	text-decoration-color: var(--color-background);
}

.container {
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

.container span {
	margin-top: 5px;
	font-size: 9pt;

	align-self: flex-start;
}
</style>
