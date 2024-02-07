<script setup lang="ts">
import { ref } from 'vue';
import { FormKit } from "@formkit/vue";
import { supabase } from '@/supabase';
import type { SchemaOffreMaison } from '@/types';
import AfficheMaison from '@/components/AfficheMaison.vue';

const maison = ref<SchemaOffreMaison>({}); // maison est un objet de type SchemaOffreMaison

async function upsertMaison(dataForm, node) {
    const { data, error } = await supabase.from("Maison").upsert(dataForm);
    if (error) node.setErrors([error.message])
}
</script>

<template>
    <div class="flex flex-col items-center">
        <h1 class="text-3xl font-bold">Ajouter une maison</h1>
        <button @click="maison" class="bg-blue-500 text-white p-2 rounded mt-4">Ajouter</button>

<div class="p-2">
            <FormKit :config="{
                classes: {
                    input: 'p-1 rounded border-gray-300 shadow-sm border-2 ',
                    label: 'text-gray-600 italic',
                    outer: 'py-2',
                },
            }" type="form" v-model="maison" @submit="upsertMaison">
                <FormKit name="nomMaison" label="Nom de la maison" type="text" />
                <FormKit name="prix" label="Prix" type="number" />
                <FormKit name="adresse" label="Adresse" type="text" />
                <FormKit name="nbrChambres" label="Nombre de chambres" type="number" />
                <FormKit name="nbrSDB" label="Nombre de salles de bain" type="number" />
                <FormKit name="favori" label="mettre en valeur" type="checkbox" label-class="pl-2"/>
            </FormKit>
        </div>
    </div>
</template>