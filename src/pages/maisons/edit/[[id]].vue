<script setup lang="ts">

import AfficheMaison from '@/components/AfficheMaison.vue';
import { ref } from "@vue/reactivity";
import { FormKit } from "@formkit/vue";
import type { SchemaOffreMaison } from '@/types';

const maison = ref<SchemaOffreMaison>({}); // maison est un objet de type SchemaOffreMaison
</script>

<template>
    <div>
        <div class="p-2">
            <h2 class="text-2xl font-bold">Résultat (Prévisualisation)</h2>
            <AfficheMaison v-bind="maison" />
        </div>
        <div class="p-2">
            <FormKit :config="{
                classes: {
                    input: 'p-1 rounded border-gray-300 shadow-sm border-2 ',
                    label: 'text-gray-600 italic',
                    outer: 'py-2',
                },
            }" type="form" v-model="maison">
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
