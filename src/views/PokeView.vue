<script setup>
import { useRoute, useRouter } from 'vue-router';
import { useGetData } from '@/composables/getData'
import { useFavoritosStore } from '@/store/favoritos'

const route = useRoute();
const router = useRouter();
const useFavoritos = useFavoritosStore()

const { add, findPoke } = useFavoritos;

const { getData, data, loading, errorData } = useGetData();

const back = () => {
    router.push('/pokemons')
};

getData(`https://pokeapi.co/api/v2/pokemon/${route.params.poke}`);
</script>


<template>
    <p v-if="loading">Cargando información...</p>

    <div class="alert alert-danger mt-2" v-if="errorData">{{ errorData }}</div>
    <div v-if="data">
        <div class="box mt-2">
            <div v-if="data">
                <img :src="data.sprites?.front_default" style="width: 200px" alt="">
                <h1>{{ $route.params.poke }}</h1>

            </div>
            <h1 v-else>No existe el pokemon</h1>
        </div>
    </div>

    <div class="mt-2">
        <button class="btn btn-primary me-2" :disabled="findPoke(data.name)" @click="add(data)">Agegar favoritos</button>
        <button @click="back" class="btn btn-outline-primary">Volver</button>
    </div>
</template>

<style>
.box {
    border: 3px solid #333333;
    background-color: hsl(196, 26%, 63%);
}
</style>