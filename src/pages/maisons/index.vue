<script setup lang="ts">
import AfficheMaison from '@/components/AfficheMaison.vue';
import type { SchemaOffreMaison } from '@/types';
import { supabase } from '@/supabase';
console.log("supabase :", supabase); // pour vérifier et "garder" supabase dans le code



let { data: tableaumaisons, error } = await supabase
    .from('Maison')
    .select('*')


</script>

<template>
    <div class="margin-auto justify-center">

    </div>
    <div class="grid grid-cols-3 gap-4">
        <AfficheMaison v-for="maison in tableaumaisons" v-bind="maison"/>
    </div>
</template>