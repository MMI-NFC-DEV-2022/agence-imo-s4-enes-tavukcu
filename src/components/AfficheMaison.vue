<script setup lang="ts">
import icon1 from './icon/icon1.vue';
import icon2 from './icon/icon2.vue';
import icon3 from './icon/icon3.vue';
import icon4 from './icon/icon4.vue';
import icon5 from './icon/icon5.vue';
import { defineProps } from 'vue';
import { SchemaOffreMaison } from '@/types';
defineProps<SchemaOffreMaison>()
</script>


<template>
  <div
    class="flex-col justify-start items-start w-[387px] h-[417px] relative rounded-lg bg-white border-[1.5px] border-indigo-100 overflow-hidden mt-20 flex m-auto justify-center">
    <div class="self-stretch flex-grow-0 flex-shrink-0 h-[200px]">
      <div class="w-[387px] h-[200px] absolute left-[-0.5px] top-[-0.5px] rounded-tl-lg rounded-tr-lg bg-[#130f26]"></div>
      <img :src="image" class="w-[387px] h-[235px] absolute left-[-0.5px] top-[-24.5px] object-cover" />
    </div>
    <div
      class="flex flex-col justify-start items-start self-stretch flex-grow-0 flex-shrink-0 relative gap-[15px] px-5 py-[30px]">
      <div class="flex justify-start items-start self-stretch flex-grow-0 flex-shrink-0 relative gap-[15px]">
        <div class="flex flex-col justify-start items-start flex-grow relative gap-2.5">
          <div class="flex justify-start items-end flex-grow-0 flex-shrink-0 w-[197.07px] relative gap-0.5">
            <p class="flex-grow-0 flex-shrink-0 text-2xl font-bold text-left text-indigo-500">
              {{ prix }}
            </p>
            <p class="flex-grow-0 flex-shrink-0 w-[58px] h-8 text-base text-left text-gray-500">
              /month
            </p>
          </div>
          <p class="flex-grow-0 flex-shrink-0 w-[299px] h-8 text-2xl font-semibold text-left text-gray-900">
            {{ nomMaison }}
          </p>
        </div>
        <icon1 :class="{ 'fill-red-600': favori }" />
      </div>
      <p class="self-stretch flex-grow-0 flex-shrink-0 w-[347px] text-base text-left text-gray-500">
        {{ adresse }}
      </p>
      <icon2 />

      <div class="flex justify-center items-center self-stretch flex-grow-0 flex-shrink-0 gap-1.5">
        <div class="flex justify-start items-center flex-grow relative gap-2">
          <icon3 />

          <p class="flex-grow-0 flex-shrink-0 text-xs text-left text-gray-600"> {{ nbrChambres }} </p>
        </div>
        <div class="flex justify-center items-center flex-grow relative gap-2">

          <icon4 />
          <p class="flex-grow-0 flex-shrink-0 text-xs text-left text-gray-600"> {{ nbrSDB }} </p>
        </div>
        <div class="flex justify-end items-center flex-grow relative gap-2">

          <icon5 />
          <p class="flex-grow-0 flex-shrink-0 text-xs text-left text-gray-600"> {{ surface }} </p>
        </div>
      </div>
    </div>
  </div>
</template>