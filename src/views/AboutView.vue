<script setup>

import { ref, onMounted, reactive, computed, watch } from 'vue';

// data
const counter = ref(0); 
const saluto = ref('ciao'); 

const state = reactive({
  name: 'Ugo',
  lastname: 'De Ughi'
})

// methods
const formatSaluto = () => {
  console.log('Ciao ' + state.name + ' ' + state.lastname);;
}

// 
onMounted(()=>{
  console.log('Il contatore è: ' + counter.value);
  console.log('Utente: ' + state.name);
})

// computed
const salutoCompleto = computed(()=> 'Ciao ' + state.name + ' ' + state.lastname )

// watch
watch(counter, (newCounter) => {
  console.log('Il contatore è diventato: ' + newCounter);
})

</script>



<template>
  <div class="">
    <h1>Contatore = {{ counter }} {{ saluto }} {{ state.name }}</h1>
    <h2>{{ salutoCompleto }}</h2>
    <button @click="counter++">+</button> <br>
    <button @click="formatSaluto">saluta</button> <br>
    <input type="text" v-model="saluto">
  </div>
</template>

<style>
@media (min-width: 1024px) {
  .about {
    min-height: 100vh;
    display: flex;
    align-items: center;
  }
}
</style>
