<script setup>
import { computed, defineProps, inject } from 'vue';

const props = defineProps({
  client: Object,
  sales: Array,
});

const totalAmount = computed(() => {
  return props.sales.reduce((sum, obj) => sum + (obj.amount || 0), 0);
});

const darkTheme = inject('darkTheme');
</script>


<template>
    <div :class="{ 'filter invert': darkTheme }" class="">
      <div class="p-8 overflow-hidden text-center shadow-sm dark:bg-blue-900 sm:rounded-lg"> 
        <h3 :class="{ 'text-gray-700': !darkTheme, 'text-black': darkTheme }" class="mb-2 text-xl font-semibold text-gray-700 dark:text-gray-50">Sales Transactions</h3>
        <table class="w-full border-collapse">
          <thead>
            <tr :class="{ 'text-gray-700': !darkTheme, 'text-black': darkTheme }" class="bg-gray-500 dark:bg-slate-900 dark:text-white">
              <th class="px-4 py-2 text-center">Date</th>
              <th class="px-4 py-2 text-center">Cash/Credit</th>
              <th class="px-4 py-2 text-center">Total</th>
            </tr>
          </thead>
          <tbody>
            <tr :class="{ 'text-gray-700': !darkTheme, 'text-black': darkTheme }" v-for="sale in sales" :key="sale.id" class="border-b border-gray-500 dark:border-gray-500">
              <td :class="{ 'text-gray-700': !darkTheme, 'text-black': darkTheme }" class="px-4 py-2 dark:text-white">{{ sale.date }}</td>
              <td :class="{ 'text-gray-700': !darkTheme, 'text-black': darkTheme }" class="px-4 py-2 dark:text-white">{{ sale.is_credit ? 'Credit' : 'Cash' }}</td>
              <td :class="{ 'text-gray-700': !darkTheme, 'text-black': darkTheme }" class="px-4 py-2 dark:text-white">{{ sale.amount }}</td>
            </tr>
            <tr>
              <td colspan="2" class="px-4 py-2 font-semibold text-right dark:text-white">Total:</td>
              <td class="px-4 py-2 text-xl font-semibold dark:text-white">{{ totalAmount }}</td> 
            </tr>
          </tbody>
        </table>
      </div>
    </div>
  </template>
