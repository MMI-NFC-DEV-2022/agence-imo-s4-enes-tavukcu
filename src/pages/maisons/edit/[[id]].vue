<script setup lang="ts">

import AfficheMaison from '@/components/AfficheMaison.vue';
import { ref } from "@vue/reactivity";
import { FormKit } from "@formkit/vue";
import type { SchemaOffreMaison } from '@/types';
import Form from '@/components/Form.vue';
import { useRoute } from 'vue-router/auto'
const route = useRoute('/maisons/edit/[[id]]')

const maison = ref<SchemaOffreMaison>({}); // maison est un objet de type SchemaOffreMaison
// console.log(route.params.id)
</script>

<template>


    <AfficheMaison :maison="maison" />
    <Form/>

</template>
