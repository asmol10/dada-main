<template>
  <q-page padding>
    <!-- Input 1: Ime klijenta -->
    <q-input 
      rounded 
      outlined 
      v-model="imeKlijenta" 
      label="Ime klijenta" 
    />

    <!-- Input 2: Odredište -->
    <q-input 
      rounded 
      outlined 
      class="q-mt-md"
      v-model="odrediste" 
      label="Odredište" 
    />

    <!-- Button -->
    <q-btn 
      label="Prikaži podatke" 
      color="primary" 
      @click="printInfo"
      class="q-mt-md"
    />

    <!-- Display values -->
    <div class="q-mt-md">
      <strong>Ime klijenta:</strong> {{ imeKlijentaDisplay }}
    </div>

    <div class="q-mt-sm">
      <strong>Odredište:</strong> {{ odredisteDisplay }}
    </div>
  </q-page>
</template>

<script setup>
import { ref } from 'vue'

// Reactive variables for inputs
const imeKlijenta = ref('')
const odrediste = ref('')

// Reactive variables for display
const imeKlijentaDisplay = ref('')
const odredisteDisplay = ref('')

// Function triggered by button
function printInfo() {
  imeKlijentaDisplay.value = imeKlijenta.value
  odredisteDisplay.value = odrediste.value
  
  console.log('Ime klijenta:', imeKlijenta.value)
  console.log('Odredište:', odrediste.value)
}
</script>