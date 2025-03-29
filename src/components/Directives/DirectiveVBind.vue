/**
 * Author:    Davi Bacalhau (littlesekii)
 * Purpose:   Understand and use Vue 3 v-bind directive.
 * 
 **/

<script setup>
import { ref } from 'vue';

const imageSrc = ref("https://picsum.photos/600/400");
const imageSmallSrc = ref("https://picsum.photos/300/200");

const showImageSmall = ref(false);
</script>

<template>
    <div class="container">
        <img v-bind:src="imageSrc" alt="">

        <!-- Directive name can be ommited +conditional class bonus using v-bind directive -->
        <img :src="imageSmallSrc" alt="" :class="{'hidden':!showImageSmall}" >
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

.container img:last-child {
    margin-top: 20px;
}

.hidden {
    display: none;
}
</style>

