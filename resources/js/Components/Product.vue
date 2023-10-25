<script setup>
import { defineProps, inject } from 'vue';

const { product } = defineProps(['product']);
const darkTheme = inject('darkTheme');
</script>

<template>
<div class="flex items-center justify-center p-4 border border-gray-300">
  <div class="overflow-hidden rounded-lg w-72 h-96">
    <img class="object-cover w-full h-3/4" :src="product.thumbnail" alt="">
    <div :class="{ 'text-gray-700': !darkTheme, 'text-white': darkTheme }" class="p-1">
      <h2 class="mb-1 text-sm font-semibold "><b class="">Name:</b> {{ product.name }}</h2>
      <h2 class="mb-1 text-sm font-semibold "><b class="">Category:</b> {{ product.category }}</h2>
      <h2 class="text-sm font-semibold"><b class="">Retail Price:</b> {{ product.retail_price }}</h2>
    </div>
  </div>
</div>


</template>


