/**
* Author: Davi Bacalhau (littlesekii)
* Purpose: Understand and use Vue 3 computed properties.
*
**/

<script setup>
import { computed, reactive, ref } from 'vue';

const person = reactive({
	firstName: "Davi",
	lastName: "Bacalhau" 
});

const users = reactive([
	{
		username: "littlesekii",
		online: true
	},
	{
		username: "flavii",
		online: true
	},
	{
		username: "wessun",
		online: false
	},
	{
		username: "baqueilhous",
		online: true
	},
	{
		username: "santhentic",
		online: false
	},
]);

const fullName = computed(() => {
	return person.firstName + " " + person.lastName;
});

const onlineUsers = computed(() => {
	return users.filter((user) => user.online);
});

const offlineUsers = computed(() => {
	return users.filter((user) => !user.online);
});

</script>

<template>
	<div class="container">
		<h2>{{ fullName }}'s group</h2>

		<h3>Online users</h3>

		<p v-for="user in onlineUsers">{{ user.username }}</p>

		<h3>Offline users</h3>

		<p v-for="user in offlineUsers">{{ user.username }}</p>

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

.container h2 {
	margin-bottom: 10px;
}

.container h3 {
	margin: 10px 0px;
}

</style>
