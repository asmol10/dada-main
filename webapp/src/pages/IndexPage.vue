<template>
  <q-page padding>
    <!-- Input field -->
    <q-input 
      rounded 
      outlined 
      v-model="naziv" 
      label="Bike name" 
    />

    <!-- Button to trigger printing -->
    <q-btn 
      label="Print Bike Name" 
      color="primary" 
      @click="printName"
      class="q-mt-md"
    />

    <!-- Display the value -->
    <div class="q-mt-md">
      <strong>Bike Name:</strong> {{ nazivDisplay }}
    </div>
  </q-page>
</template>

<script setup>
import { ref } from 'vue'

// Reactive variable bound to input
const naziv = ref('')

// Variable to store printed output
const nazivDisplay = ref('')

// Function to “print” the name
function printName() {
  nazivDisplay.value = naziv.value
  console.log('Bike name:', naziv.value) // also prints to browser console
}
</script>