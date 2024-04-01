<script setup>

import { ref } from 'vue'
import BodyMassIndexForm from './components/BodyMassIndexForm.vue' // imports child BodyMassIndexForm.vue

const bmi = ref('')
const calculateBMI = (height, weight) => {  // function that takes height and weight inputs and
  bmi.value = (weight / (height * height)).toFixed(2) // calculates the bmi value to 2 decimal places
 }

</script>

<template>
  <!-- here's the HTML for the component -->
  <div id="app-component">
    <h1> Body Mass Index Calculator</h1>
  </div>
  <!-- v-on click handler that runs when stats-entered is function is called from child component -->
  <BodyMassIndexForm

    v-on:stats-entered="calculateBMI"
    ></BodyMassIndexForm>

    <p> Your BMI is: {{ bmi }}  </p>

</template>

<style scoped>

</style>
