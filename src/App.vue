<script setup>
import { RouterLink, RouterView } from "vue-router";
</script>

<template>
  <nav class="navbar navbar-expand-lg navbar-dark bg-dark shadow-sm">
    <div class="container-fluid">
      <!-- Logo y Título -->
      <router-link class="navbar-brand d-flex align-items-center" to="/">
        <img
          src="@/assets/logo.svg"
          alt="Logo"
          width="30"
          height="30"
          class="d-inline-block align-text-top me-2"
        />
        <span class="fw-bold">PokeAPI</span>
      </router-link>

      <!-- Botones de navegación (colapsables) -->
      <button
        class="navbar-toggler"
        type="button"
        data-bs-toggle="collapse"
        data-bs-target="#navbarNav"
        aria-controls="navbarNav"
        aria-expanded="false"
        aria-label="Toggle navigation"
      >
        <span class="navbar-toggler-icon"></span>
      </button>

      <div class="collapse navbar-collapse" id="navbarNav">
        <ul class="navbar-nav ms-auto">
          <li class="nav-item">
            <router-link class="nav-link btn btn-outline-primary me-2" to="/">
              Home
            </router-link>
          </li>
          <li class="nav-item">
            <router-link class="nav-link btn btn-outline-secondary" to="/pokemons">
              Pokemons
            </router-link>
          </li>
          <li class="nav-item">
            <router-link class="nav-link btn btn-outline-secondary" to="/favoritos">
              Favoritos
            </router-link>
          </li>
        </ul>
      </div>
    </div>
  </nav>

  <!-- Contenedor principal -->
  <div class="container mt-4">
    <RouterView />
  </div>
</template>

<style scoped>
/* Estilo personalizado para el navbar */
.navbar {
  background-color: #f8f9fa;
}

.navbar-brand span {
  font-size: 1.25rem;
  color: #000000;
}

.nav-link {
  text-transform: capitalize;
}

.navbar-toggler {
  border-color: #007bff;
}

/* Contenedor principal */
.container {
  max-width: 960px;
  background: #ffffff;
  border-radius: 10px;
  box-shadow: 0px 4px 8px rgba(0, 0, 0, 0.1);
  padding: 20px;
}

/* Animación para el contenido */
.container {
  animation: fadeIn 0.5s ease-in-out;
}

@keyframes fadeIn {
  from {
    opacity: 0;
    transform: translateY(10px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}
</style>
