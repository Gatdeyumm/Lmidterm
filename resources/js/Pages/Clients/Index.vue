<script setup>
import AuthenticatedLayout from '@/Layouts/AuthenticatedLayout.vue';
import ClientCard from '@/Components/ClientCard.vue';
import { Head } from '@inertiajs/vue3';
import { defineProps } from 'vue';

const { clients } = defineProps(['clients']);
</script>

<template>
    <Head title="Clients" />

    <AuthenticatedLayout>
        <div>
            <div class="flex flex-wrap justify-center m-5">
                <ClientCard v-for="client in clients" :key="client.id" :client="client" class="p-5 m-10 rounded-lg shadow-lg" />
            </div>
        </div>


    </AuthenticatedLayout>
</template>
