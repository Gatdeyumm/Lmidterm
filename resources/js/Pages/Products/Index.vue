<script setup>
import AuthenticatedLayout from '@/Layouts/AuthenticatedLayout.vue';
import { Head, Link, usePage } from '@inertiajs/vue3';
import Product from '@/Components/Product.vue';

import { defineProps, inject } from 'vue';

const darkTheme = inject('darkTheme');

const page = usePage();

const { products } = defineProps(['products']);
</script>

<template>
  <Head title="Products" />

  <AuthenticatedLayout>
    <div>
      <div class="flex justify-end m-10">
        <Link :href="route('product.create')" class="p-2 text-white transition duration-300 rounded-lg pe-4 ps-4 bg-slate-500 hover:bg-slate-600">
          Add Product
        </Link>
      </div>

        <div class="flex flex-wrap justify-center m-5">
            <Product
            v-for="product in products"
            :key="product.id"
            :product="product"
            class="p-5 m-10 rounded-lg shadow-xl"
          />

        </div>
    </div>

  </AuthenticatedLayout>
</template>
