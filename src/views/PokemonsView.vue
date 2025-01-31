<script setup>
import { RouterLink } from 'vue-router';
import {useGetData} from '@/composables/getData'

const {data, getData, loading, error} = useGetData()
getData("https://pokeapi.co/api/v2/pokemon");

</script>

<template>
  <div class="container mt-4">
    <h2 class="text-center mb-4">Pokemons</h2>
    <p v-if="loading">Cargando informacion...</p>
    <div class="alert alert-danger" v-if="error">{{ error }}</div>
    <div v-if="data">
      <ul class="list-group">
      <li v-for="poke in data.results" :key="poke.name" class="list-group-item d-flex justify-content-between align-items-center">
        <router-link :to="`/pokemons/${poke.name}`" class="text-decoration-none text-dark">
          {{ poke.name }}
        </router-link>
      </li>
    </ul>
    <div class="mt-2">
      <button :disabled="!data.previous"
    class="btn btn-warning me-2" 
    @click="getData(data.previous)"
    >
    Previous
    </button>

    <button 
    :disabled="!data.next"
    class="btn btn-success" 
    @click="getData(data.next)"
    >Next</button>

    </div>
    </div>
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
