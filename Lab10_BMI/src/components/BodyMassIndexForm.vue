<script setup>
import { ref } from 'vue'

defineProps({
  // extra question needs this, the basic app does not

})

// define the message that this component may send to other components
const emit = defineEmits(['stats-entered'])

const height = ref('0')
const weight = ref('0')

function statsEntered() {  // defines function that emits height and weight values to parent app.vue
  emit('stats-entered', height.value, weight.value) // emits to App.vue - components parent
}
</script>

<template>

  <label> Enter your height in meters</label>
  <input v-model="height">  <!-- binds user input to height ref using v-model-->

  <br>

  <label> Enter your weight in kilograms </label>
  <input v-model="weight"> <br> <br> <!-- binds user input to weight ref using v-model-->

  <button v-on:click="statsEntered"> Calculate </button>  <!-- click event listener that calls statsEntered function -->

</template>


<style scoped>
button{
  font-size: 17px;
  padding: 15px;
  background-color: mediumpurple;
  border-radius: 10px;
  color: white;
}

</style>
