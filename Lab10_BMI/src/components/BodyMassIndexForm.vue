<script setup>
import { ref } from 'vue'

defineProps({
  // extra question needs this, the basic app does not

})

// define the message that this component may send to other components
const emit = defineEmits(['stats-entered'])

// we can pick the above names - this message will be sent once the user has entered their data and the app should do the math

const height = ref('0')
const weight = ref('0')

function statsEntered() {
  alert('is this working?')
  // todo send this data - height and weight to App.vue to do the math
  // make sure to include weight

  emit('stats-entered', height.value, weight.value) // goes to this components parent
}
</script>

<template>
  <label> Height</label>
  <input v-model="height">

  <label> Weight</label>
  <input v-model="weight"> <br> <br>

  <button v-on:click="statsEntered"> Calculate </button>



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
