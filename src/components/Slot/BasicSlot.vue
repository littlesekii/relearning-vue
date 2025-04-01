/**
* Author: Davi Bacalhau (littlesekii)
* Purpose: Understand and use Vue 3 slot.
*
**/

<script setup>

</script>

<template>
	<div class="container">
		<slot name="header"></slot>
    <br><br>
    <slot></slot>
    <br><br>
    <slot name="footer"></slot>
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
