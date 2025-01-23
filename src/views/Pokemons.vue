<script setup>
import axios from 'axios';
import { ref } from 'vue';
import { RouterLink } from 'vue-router';

const pokemons = ref([]);

const getData = async () => {
  try {
    const { data } = await axios.get(`https://pokeapi.co/api/v2/pokemon`);
    console.log(data.results);
    pokemons.value = data.results; // Asegúrate de que `data.results` sea un array válido
  } catch (error) {
    console.error("Error fetching Pokémon data:", error);
  }
};

getData();
</script>

<template>
  <div class="container mt-4">
    <h2 class="text-center mb-4">Pokemons</h2>
    <ul class="list-group">
      <li v-for="poke in pokemons" :key="poke.name" class="list-group-item d-flex justify-content-between align-items-center">
        <router-link :to="`/pokemons/${poke.name}`" class="text-decoration-none text-dark">
          {{ poke.name }}
        </router-link>
      </li>
    </ul>
  </div>
</template>

<style scoped>
.container {
  max-width: 600px;
  margin: auto;
}

h2 {
  color: #000000;
}

.list-group-item {
  transition: transform 0.2s ease, background-color 0.3s ease;
}

.list-group-item:hover {
  transform: scale(1.02);
  background-color: #c1d6cc;
}

.text-dark {
  font-weight: bold;
}

.badge {
  font-size: 0.9rem;
}
</style>
