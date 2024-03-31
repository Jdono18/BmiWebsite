<script setup>

import { ref } from 'vue'
import BodyMassIndexForm from './components/BodyMassIndexForm.vue'

const height = ref('')
const weight = ref('')
const bmi = ref(0)
const calculateBMI = (height, weight) => {
  const bmi = weight / (height * height)
  alert(`todo - do math! height is ${height} , ${weight} your BMI is ${bmi}`)
}

</script>

<template>
  <!-- here's the HTML for the component -->
  <div id="app-component">
    <h1> Body Mass Index Calculator</h1>


  </div>

  <BodyMassIndexForm
      v-on:stats-entered="calculateBMI"
      ></BodyMassIndexForm>

  <p> Your BMI is: {{ bmi }}  </p>

</template>

<style scoped>


</style>
