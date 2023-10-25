<script setup>
import { defineProps, inject } from 'vue';

const props = defineProps({
  client: Object,
});

const darkTheme = inject('darkTheme');
</script>

<template>
   <div :class="{ 'text-black': !darkTheme, 'text-white': darkTheme }">
  <div class="p-4 m-4 rounded-lg shadow-sm" :class="{ 'bg-gray-300': !darkTheme, 'bg-gray-700': darkTheme }">
    <h1 class="mb-4 text-xl font-semibold"><b class="p-2">Name:</b> {{ client.first_name }} {{ client.last_name }}</h1>
    <h1 class="mb-4 text-xl font-semibold"><b class="p-2">Address:</b> {{ client.address }}</h1>
    <h1 class="mb-4 text-xl font-semibold"><b class="p-2">Phone:</b> {{ client.phone }}</h1>
    <h1 class="text-xl font-semibold"><b class="p-2">Credit Limit:</b> {{ client.credit_limit }}</h1>
  </div>
</div>

  </template>
