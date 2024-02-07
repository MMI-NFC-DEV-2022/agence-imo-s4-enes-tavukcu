<script setup lang="ts">
import { RouterLink, RouterView } from 'vue-router'
</script>

<template>
  <header>
    <div class="flex justify-center items-center">
      <h1 class="text-transform: uppercase font-style: italic font-weight: 700 text-4xl">Bienvenue à l'agence IMOO</h1>
      <img src="https://www.zarla.com/images/zarla-chez-moi-1x1-2400x2400-20210604-f679vdw9h3yckr9wmqkv.png?crop=1:1,smart&width=250&dpr=2" class="w-20 h-20" alt="logo" />
    </div>

    <nav class="*:drop-shadow-lg flex p-2 text-stone-400 m-auto justify-center">
      <RouterLink to="/" class="p-2 hover:scale-110 hover:text-black">Home</RouterLink>
      <RouterLink to="/about" class="p-2 hover:scale-110 hover:text-black">About</RouterLink>
      <RouterLink to="/simple" class="p-2 hover:scale-110 hover:text-black">LA CARD </RouterLink>
      <RouterLink to="/connexion" class="p-2 hover:scale-110 hover:text-black">Connexion</RouterLink>
      <RouterLink to="/maisons" class="p-2 hover:scale-110 hover:text-black">Maison</RouterLink>
      <RouterLink to="/maisons/edit" class="p-2 hover:scale-110 hover:text-black">AYRTON AJOUUUUUTE GROOOOS</RouterLink>
    </nav> 
  </header>

<Suspense>
  <RouterView />
</Suspense>
  
</template>

<style>
  header {
    background-color: #f3f4f6;
    padding: 1rem;
    text-align: center;
    box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
  }
  .RouterLink {
    background-color: #f3f4f6;
    padding: 1rem;
    text-align: center;
    box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
    animation: fadeIn 0.3s ease-in-out;
  }
  .RouterLink:hover {
    background-color: #f3f4f6;
    padding: 1rem;
    text-align: center;
    box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
    animation: fadeIn 0.3s ease-in-out;
    scale: 1.1;
  }
</style>