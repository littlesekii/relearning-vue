<script setup>
import { RouterView } from 'vue-router'
</script>

<template>
  <main>
    <RouterView />
  </main>
</template>

<style scoped>
  main {
    height: 100vh;

    display: flex;
    justify-content: center;
    align-items: center;
  }
</style>
