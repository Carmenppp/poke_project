<script setup>
import { useRouter } from 'vue-router';
  const router = useRouter()
  const volver = () => {
    router.push(`/pokemons`)
  }

</script>

<template>
    <h1>404</h1>
    <button @click="volver" class="btn btn-outline-primary">Volver a pagina</button>
</template>