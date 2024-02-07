<script setup lang="ts">
import AfficheMaison from '@/components/AfficheMaison.vue';
import type { SchemaOffreMaison } from '@/types';
const tableaumaisons = [{
    nomMaison: 'Maison1',
    prix: 1000,
    adresse: '14543 rue',
    nbrChambres: 2,
    nbrSDB: 2,
    surface: "30x40m²",
    favori: true,
    image: 'pexels-binyamin-mellish-106399 1 (5).png'
},
{
    nomMaison: 'Maison2',
    prix: 1000,
    adresse: '123 rue',
    nbrChambres: 3,
    nbrSDB: 2,
    surface: "30x40m²",
    favori: true,
    image: 'pexels-binyamin-mellish-106399 1 (5).png'
},
{
    nomMaison: 'Maison3',
    prix: 1000,
    adresse: '123 rue',
    nbrChambres: 3,
    nbrSDB: 2,
    surface: "30x40m²",
    favori: true,
    image: 'pexels-binyamin-mellish-106399 1 (5).png'
},
{
    nomMaison: 'Maison4',
    prix: 1000,
    adresse: '123 rue',
    nbrChambres: 3,
    nbrSDB: 2,
    surface: "30x40m²",
    favori: true,
    image: 'pexels-binyamin-mellish-106399 1 (5).png'
},
{
    nomMaison: 'Maison5',
    prix: 1000,
    adresse: '123 rue',
    nbrChambres: 3,
    nbrSDB: 2,
    surface: "30x40m²",
    favori: true,
    image: 'pexels-binyamin-mellish-106399 1 (5).png'
},
{
    nomMaison: 'Maison6',
    prix: 1000,
    adresse: '123 rue',
    nbrChambres: 3,
    nbrSDB: 2,
    surface: "30x40m²",
    favori: true,
    image: 'pexels-binyamin-mellish-106399 1 (5).png'
},
]
const maMaison:SchemaOffreMaison = {
    nomMaison: 'Maison2',
    prix: 1000,
    adresse: '123 rue',
    nbrChambres: 3,
    nbrSDB: 2,
    surface: "30x40m²",
    favori: true,
    image: 'pexels-binyamin-mellish-106399 1 (5).png'
}
</script>

<template>
    
    <div class="margin-auto justify-center">
        
        <AfficheMaison nom-maison="Maison" :favori="true" image="\public\pexels-binyamin-mellish-106399.jpg"/>
    </div>
    <div class="grid grid-cols-3 gap-4">
    <AfficheMaison v-for="maison in tableaumaisons" :nom-maison="maison.nomMaison" :prix="maison.prix" :adresse="maison.adresse" :nbrChambres="maison.nbrChambres" :nbrSDB="maison.nbrSDB" :surface="maison.surface" :favori="maison.favori" :image="maison.image"/>
    </div>
</template>