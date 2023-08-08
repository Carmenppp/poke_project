<script setup>
import {useFavoritoStore} from '@/store/favoritos'
import { storeToRefs } from 'pinia';
import { RouterLink } from 'vue-router';



const useFavorito = useFavoritoStore()
const {favoritos} = storeToRefs(useFavorito)
const {remove} = useFavorito

</script>

<template>
    <h1>Favoritos</h1>
    <p v-if="favoritos.length === 0">Sin favoritos</p>
    <ul class= "list-group" v-else>
        <li class="list-group-item"
        v-for="poke in favoritos" key="poke.id">
        <div>
            {{ poke.name }}
        </div>
        <div>
            <button class="btn btn-sm btn btn-danger" @click="remove(poke.id)">Eliminar</button>
            <RouterLink class="btn btn-primary ms-2" :to="`/pokemons/${poke.name}`">Mayor informacion</RouterLink>
        </div>
        </li>
    </ul>
</template>