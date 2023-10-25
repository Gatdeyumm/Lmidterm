<script setup>
import { defineProps, inject } from 'vue';

const { user } = defineProps(['user']);
const darkTheme = inject('darkTheme');
</script>

<template>
<div :class="{ 'text-gray-700': !darkTheme, 'text-white': darkTheme  }" class="p-6 text-center border rounded-lg shadow-sm w-150 border-primary">
  <h1 class="mb-4 text-2xl font-semibold">
    <i class="mr-3 text-primary fas fa-id-badge"></i> {{ user.id }}
  </h1>
  <h1 class="mb-4">
    <i class="mr-3 text-primary fas fa-user"></i> <b>Name:</b> {{ user.name }}
  </h1>
  <h1>
    <i class="mr-3 text-primary fas fa-envelope"></i> <b>Email:</b> {{ user.email }}
  </h1>
</div>



</template>
