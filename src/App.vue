<script setup>
import Pokemon from './services/apiPokemon.js';
import { ref, onBeforeMount } from 'vue';
import CardPokemon from './components/CardPokemon.vue';


const service = new Pokemon([]);

let pokemons = ref([]);

onBeforeMount(async()=>{
    pokemons.value = await service.fetchAll()
    console.log(pokemons.value);

})

</script>

<template>
  <!-- <h1>Pokemons</h1>
  <ul>
    <li v-for="pokemon in pokemons">{{ pokemon }}</li>
  </ul> -->

  <CardPokemon/>
</template>

<style scoped>

</style>
