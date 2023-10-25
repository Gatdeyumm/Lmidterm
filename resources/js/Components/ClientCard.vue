<script setup>
import { defineProps, inject } from 'vue';
import { router } from '@inertiajs/vue3';

const props = defineProps({
    client: Object,
});

const darkTheme = inject('darkTheme');

const viewClient = () => {
    router.get('/client/view/' + props.client.id);
};
</script>

<template>
<div @click="viewClient" style="cursor: pointer;" class="h-[200px] w-[300px] m-2 p-3 border border-gray-300 hover:shadow-md rounded-lg transition duration-300">
  <div :class="{ 'text-gray-700': !darkTheme, 'text-white': darkTheme }">
    <div class="my-3 text-center">
      <h3 class="text-lg font-semibold">{{ client.first_name }} {{ client.last_name }}</h3>
      <p class="my-2 text-sm">Address: {{ client.address }}</p>
    </div>
    <div class="flex flex-col">
      <div class="my-1">
        <span class="text-sm font-semibold">Phone:</span> {{ client.phone }}
      </div>
      <div class="my-1">
        <span class="text-sm font-semibold">Credit Limit:</span> {{ client.credit_limit }}
      </div>
    </div>
  </div>
</div>




    <!-- <div class="min-w-[350px] mb-4 mx-2 p-4 bg-white rounded shadow border flex-1 cursor-pointer" @click="viewClient" :class="{ 'filter invert': darkTheme }">
        <h5 class="flex items-center mb-2 text-2xl font-bold tracking-tight" :class="darkTheme ? 'text-black' : 'text-gray-700'">
            {{ client.first_name }} {{ client.last_name }}
        </h5>
        <div class="mb-2">
            <p class="text-sm font-semibold" :class="darkTheme ? 'text-black' : 'text-gray-700'">Address</p>
            <p class="text-sm font-light" :class="darkTheme ? 'text-black' : 'text-gray-700'">{{ client.address }}</p>
        </div>
        <div class="mb-2">
            <p class="text-sm font-semibold" :class="darkTheme ? 'text-black' : 'text-gray-700'">Phone</p>
            <p class="text-sm font-light" :class="darkTheme ? 'text-black' : 'text-gray-700'">{{ client.phone }}</p>
        </div>
        <div>
            <p class="text-sm font-semibold" :class="darkTheme ? 'text-black' : 'text-gray-700'">Credit Limit</p>
            <p class="text-sm font-light" :class="darkTheme ? 'text-black' : 'text-gray-700'">{{ client.credit_limit }}</p>
        </div>
    </div> -->
</template>
