/**
 * Author:    Davi Bacalhau (littlesekii)
 * Purpose:   Understand and use Vue 3 reactivity properties. 
 * 
 **/

<script setup>
import { reactive, ref } from 'vue';

//ref function is used to primitive types
const name = ref("Davi Bacalhau");
const age = ref(22);

//reactive function is used to objects/arrays
const playedGames = reactive([
    {
        name: "Chrono Trigger",
        launchYear: 1995
    },
    {
        name: "The Legend of Zelda: Tears of the Kingdom",
        launchYear: 2023
    },
    {
        name: "Shadow of the Colossus",
        launchYear: 2005
    }
]);

</script>

<template>
    <div class="container">
        
        <h1>Player ID</h1>
        <div class="player-container">
            <div class="player-info">
                <h2>{{ name }}</h2>  
                <h5>{{ age }} years</h5>  
            </div>
            <div class="player-gamelist">
                <ul>
                    <li> ({{ playedGames[0].launchYear }}) {{ playedGames[0].name }} </li>
                    <li> ({{ playedGames[1].launchYear }}) {{ playedGames[1].name }} </li>
                    <li> ({{ playedGames[2].launchYear }}) {{ playedGames[2].name }} </li>
                </ul>
            </div>
        </div>
    </div>

</template>

<style scoped>
    .container {
        display: flex;
        flex-direction: column;

        justify-content: center;
        align-items: center;
    }
    .container h1 {
        margin-bottom: 20px;
    }

    .player-container {
        width: 100%;
        max-width: 410px;
        padding: 10px;

        border: 2px solid var(--black-light);
    }

    .player-info {
        padding-bottom: 10px;
        margin-bottom: 10px;
        
        border-bottom: 1px solid var(--black-light);
    }

    .player-gamelist ul {
        list-style: none;
        padding: 0px;
        padding: 10px;
    }
    .player-gamelist ul li {
        padding-bottom: 5px;
    }
    .player-gamelist ul li:last-child {
        padding: 0px;
    }

</style>

