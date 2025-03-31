/**
 * Author:    Davi Bacalhau (littlesekii)
 * Purpose:   Understand and use Vue 3 v-on directive.
 * 
 **/

<script setup>
import { ref } from 'vue';

const imageSrc = ref("https://picsum.photos/600/400?");

function newImage()
{
    let image = document.querySelector(".container > img");
    image.src = imageSrc.value + new Date();
}

function changeImageSize() {
    const sizes = ['100', '200', '300', '400'];
    const sizeIndex = {
        width: Math.floor(Math.random() * 4),
        height: Math.floor(Math.random() * 4)
    };
    imageSrc.value = `https://picsum.photos/${ sizes[sizeIndex.width] }/${ sizes[sizeIndex.height] }?`
}
</script>

<template>
    <div class="container">
        <img v-bind:src="imageSrc" alt="">

        <button v-on:click="newImage">New image</button>

        <!-- "v-on:" query can be also ommited by using "@" -->
        <button @click="changeImageSize">New size</button>
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

.container img {
    margin-bottom: 20px;
}

button {
    cursor: pointer;
    padding: 5px 10px;
}
button:last-child {
    margin-top: 10px;
}
</style>

