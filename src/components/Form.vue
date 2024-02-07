<script setup lang="ts">
import { ref } from 'vue';
import { FormKit } from "@formkit/vue";
import { supabase } from '@/supabase';
import type { SchemaOffreMaison } from '@/types';
import AfficheMaison from '@/components/AfficheMaison.vue';
import { useRouter, useRoute } from 'vue-router/auto';
const router = useRouter();

const maison = ref<SchemaOffreMaison>({}); // maison est un objet de type SchemaOffreMaison

async function upsertMaison(dataForm, node) {
    const { data, error } = await supabase.from("Maison").upsert(dataForm).select("id");
    if (error) node.setErrors([error.message])
    else {
        console.log("data :", data);
    }
    router.push({ name: '/maisons/edit/[[id]]', params: { id: data[0].id } });
}

const route = useRoute('/maisons/edit/[[id]]');
if (route.params.id) {
    const { data, error } = await supabase.from("Maison").select("*").eq("id", route.params.id).single();
    if (error) console.error("error", error);
    else maison.value = data;
}

</script>

<template>
    
        <AfficheMaison v-bind="maison" class="margin-auto justify-center flex" />

    <div class="flex flex-col items-center">
       

<div class="p-2">
            <FormKit :config="{
                classes: {
                    input: 'p-1 rounded border-gray-300 shadow-sm border-2 ',
                    label: 'text-gray-600 italic',
                    outer: 'py-2',
                },
            }" type="form"
             v-model="maison"
              @submit="upsertMaison">
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

<style>
    body {
        background: linear-gradient(90deg, #8a2387 0%, #e94057 100%);
        /*bg-gradient-to-r from-violet-500 to-fuchsia-500*/
    }
</style>