/**
 * Author:    Davi Bacalhau (littlesekii)
 * Purpose:   Understand and use Vue 3 v-if, v-else-if, v-else and v-show directives.
 * 
 **/

<script setup>
import { reactive, ref } from 'vue';

const grades = reactive([
    10.0,
    10.0,
    10.0,
    9.0
]);

const finalGrade = ref(0);
const showGrade = ref(true);

//CALCULATE AVERAGE
grades.forEach(grade => {
    finalGrade.value += grade;
});

finalGrade.value /= 4;

</script>

<template>
    <div class="container">

        <!-- if, else if, else -->
        <h1 v-if="finalGrade >= 7.0">
            Approved
        </h1>
        <h1 v-else-if="finalGrade <= 3.0">
            Dismissed
        </h1>
        <h1 v-else>
            Second Call
        </h1>

        <!-- show -->
        <p v-show="showGrade">Your grade: {{ finalGrade.toFixed(1) }}</p>

        <!-- loop conditional -->
        <p>Above average grades</p>
        <ul>
            <template v-for="grade, key in grades">
                <li v-if="grade >= 7.0">{{ key + 1 }}st term:  {{ grade.toFixed(1) }}</li>
            </template>
        </ul>
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

p:last-of-type {
    padding-top: 50px;
    padding-bottom: 5px;
}

ul {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: flex-start;

    align-self: flex-start;
    

    list-style: none;
}
ul li {
    margin-bottom: 2px;
    font-size: 10pt;
}
</style>

