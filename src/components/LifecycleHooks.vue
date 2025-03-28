/**
 * Author:    Davi Bacalhau (littlesekii)
 * Purpose:   Understand and use every Vue 3 lifecycle hook. 
 * 
 **/

<script setup>
import { ref, onBeforeMount, onBeforeUnmount, onBeforeUpdate, onMounted, onUnmounted, onUpdated } from 'vue';
import { RouterLink } from 'vue-router';

onBeforeMount(() => {
    console.log("Lifecycle Hooks - Before Mount");
});

onMounted(() => {
    console.log("Lifecycle Hooks - Mounted");
});

onBeforeUpdate(() => {
    console.log("Lifecycle Hooks - Before Update");
});

onUpdated(() => {
    console.log("Lifecycle Hooks - Updated");
});

onBeforeUnmount(() => {
    console.log("Lifecycle Hooks - Before Unmount");
});

onUnmounted(() => {
    console.log("Lifecycle Hooks - Unmounted");
});

let updated = ref(0);

</script>

<template>
    <div class="container">
        <div class="title">
            Lifecycle Hooks
        </div>
        <div class="buttons">
            <button @click="updated++">Update {{ updated }}</button>            
            <button @click="$router.push('unmount')">Unmount (redirect)</button>
        </div>
    </div>
</template>

<style scoped>
    .container {
        width: 200px;
        padding: 10px;
    }

    .title {
        text-align: center;
        padding: 10px;
    }

    .buttons {
        display: flex;
        flex-direction: column;  
    }
    button {
        padding: 7px 0px;
    }
    button:first-of-type {
        margin-bottom: 5px;
    }

</style>