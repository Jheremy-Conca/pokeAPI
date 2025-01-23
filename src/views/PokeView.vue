<script setup>
import axios from "axios";
import { ref } from "vue";
import { useRoute, useRouter } from "vue-router";

const route = useRoute();
const router = useRouter();

const poke = ref({});

const back = () => {
  router.push("/pokemons");
};

const getData = async () => {
  try {
    const { data } = await axios.get(
      `https://pokeapi.co/api/v2/pokemon/${route.params.name}`
    );
    poke.value = data;
  } catch (error) {
    console.log(error);
    poke.value = null;
  }
};
getData();
</script>

<template>
  <div class="container mt-5">
    <div v-if="poke" class="text-center">
      <img
        :src="poke.sprites?.front_default"
        alt="Pokemon Image"
        class="pokemon-image mb-3"
      />
      <h1 class="text-dark">{{ $route.params.name.toLocaleUpperCase() }}</h1>
      <ul class="list-group mt-4">
        <li class="list-group-item d-flex justify-content-between align-items-center">
          <strong>Height:</strong>
          <span>{{ poke.height }} decimetres</span>
        </li>
        <li class="list-group-item d-flex justify-content-between align-items-center">
          <strong>Weight:</strong>
          <span>{{ poke.weight }} hectograms</span>
        </li>
        <li class="list-group-item d-flex justify-content-between align-items-center">
          <strong>Base Experience:</strong>
          <span>{{ poke.base_experience }}</span>
        </li>
        <li class="list-group-item d-flex justify-content-between align-items-center">
          <strong>Abilities:</strong>
          <span>
            <span v-for="(ability, index) in poke.abilities" :key="index">
              {{ ability.ability.name }}<span v-if="index !== poke.abilities.length - 1">, </span>
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
