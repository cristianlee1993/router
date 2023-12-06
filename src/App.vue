<script setup>
import { RouterLink, RouterView } from 'vue-router';

</script>

<template>
  <main>
    <nav class="navbar bg-dark navbar-dark">
      <div class="container">
        <RouterLink class="navbar-brand" to="/">
          <img src="@/assets/logo.svg" alt="Logo" width="30" height="24" class="d-inline-block align-text-top">
          PokeAPI
        </RouterLink>
        <div>
          <RouterLink active-class="active" class="btn btn-outline-primary me-2" to="/">Home</RouterLink>
          <RouterLink active-class="active" class="btn btn-outline-primary me-2" to="/pokemons">Pokemons</RouterLink>
          <RouterLink active-class="active" class="btn btn-outline-primary " to="/favoritos">Favoritos</RouterLink>
        </div>
      </div>
    </nav>
    <div class="container text-center">
      <RouterView />
    </div>
  </main>
</template>

<style>
#app {
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  background-color: #182a3f;
  min-height: 100vh;
}

/* body {
  margin: 0;
  padding: 0;
} */
body{
  margin: 0; 
  padding: 0;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  background-color: #182a3f;
  min-height: 100vh;
}
</style>
