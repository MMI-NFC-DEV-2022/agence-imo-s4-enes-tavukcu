<script setup lang="ts">
import { supabase } from '@/supabase';
console.log("supabase :", supabase); // pour vérifier et "garder" supabase dans le code
const maisons = []; // à remplacer par l'appel à Supabase


let { data: Maison, error } = await supabase
    .from('Maison')
    .select('some_column,other_column')


</script>


