<script setup>
import { useRoute, useRouter } from "vue-router";
import {useGetData} from '@/composables/getData'
import { useFavoritosStore } from "@/store/favoritos";


const route = useRoute();
const router = useRouter();
const useFavoritos = useFavoritosStore()

const {add, findPoke}= useFavoritos
const {data, getData, loading, error} = useGetData()

const back = () => {
  router.push("/pokemons");
};

getData(`https://pokeapi.co/api/v2/pokemon/${route.params.name}`);
</script>

<template>
  <div class="container mt-5">
    <p v-if="loading">Cargando informacion...</p>
    <div class="alert alert-danger" v-if="error">{{ error }}</div>

    <div v-if="data" class="text-center">
      <img
        :src="data.sprites?.front_default"
        alt="Pokemon Image"
        class="pokemon-image mb-3"
      />
      <h1 class="text-dark">{{ $route.params.name.toLocaleUpperCase() }}</h1>
      <button :disabled="findPoke(data.name)" class="btn btn-primary"  @click="add(data)">Agregar Favoritos</button>
      <ul class="list-group mt-4">
        <li class="list-group-item d-flex justify-content-between align-items-center">
          <strong>Height:</strong>
          <span>{{ data.height }} decimetres</span>
        </li>
        <li class="list-group-item d-flex justify-content-between align-items-center">
          <strong>Weight:</strong>
          <span>{{ data.weight }} hectograms</span>
        </li>
        <li class="list-group-item d-flex justify-content-between align-items-center">
          <strong>Base Experience:</strong>
          <span>{{ data.base_experience }}</span>
        </li>
        <li class="list-group-item d-flex justify-content-between align-items-center">
          <strong>Abilities:</strong>
          <span>
            <span v-for="(ability, index) in data.abilities" :key="index">
              {{ ability.ability.name }}<span v-if="index !== data.abilities.length - 1">, </span>
            </span>
          </span>
        </li>
      </ul>
    </div>
    <div v-else class="text-center">
      <h1 class="text-danger">No existe el Pokémon</h1>
    </div>
    <div class="text-center mt-4">
      <button class="btn btn-outline-primary" @click="back">Volver</button>
    </div>
  </div>
</template>

<style scoped>
.container {
  max-width: 600px;
  margin: auto;
}

.pokemon-image {
  width: 150px;
  height: 150px;
  object-fit: contain;
  border: 2px solid #dee2e6;
  border-radius: 50%;
  background-color: #f8f9fa;
  padding: 10px;
}

.list-group-item {
  background-color: #f8f9fa;
  border-color: #dee2e6;
}

.btn-outline-primary:hover {
  background-color: #0d6efd;
  color: white;
}
</style>
