<script setup>
import { defineProps, inject } from 'vue';

const props = defineProps({
    sales: Array, // Ensure that this type matches the type of your sales prop
});

const darkTheme = inject('darkTheme');
</script>

<template>
<div :class="darkTheme ? 'text-white' : 'text-gray-700'" class="h-[200px] w-[300px] m-2 p-3 shadow-lg rounded-lg border border-gray-300" v-for="sale in sales" :key="sale.id">
  <div class="flex flex-col items-center justify-center h-full p-1">
    <h1 class="mb-3 text-sm font-semibold"><b class="p-2">Client ID:</b> {{ sale.id }}</h1>
    <h1 class="mb-3 text-sm font-semibold"><b class="p-2">Date:</b> {{ sale.date }}</h1>
    <h1 class="text-sm font-semibold"><b class="p-2">Credited:</b> {{ sale.is_credit ? 'Yes' : 'No' }}</h1>
  </div>
</div>


</template>
