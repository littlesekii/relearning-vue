/**
* Author: Davi Bacalhau (littlesekii)
* Purpose: Understand and use Vue 3 template ref.
*
**/

<script setup>
import { onMounted, reactive, ref, useTemplateRef } from 'vue';

const objectList = reactive([
  "Cup",
  "Bottle",
  "Knife"
]);

const containerElement = useTemplateRef("container");
const objectElements = useTemplateRef("object");

onMounted(() => {
  console.log(containerElement.value);
  console.log(containerElement.value.innerText);

  objectElements.value.map((element) => {
    console.log(element);
    console.log(element.innerText);
  });
})

</script>

<template>
  <main>
    <div class="container" ref="container">
      Some info here...
    </div>

    <div class="container">
      <ul>
        <li v-for="obj in objectList" ref="object">{{ obj }}</li>
      </ul>
    </div>
  </main>

</template>

<style scoped>
.container {
	padding: 20px;
	display: flex;
	flex-direction: column;

	justify-content: center;
	align-items: center;

	border: 1px solid var(--black-light);

  margin-top: 20px;
}

ul {
  list-style: none;
}

main {
  flex-direction: column;
}
</style>
