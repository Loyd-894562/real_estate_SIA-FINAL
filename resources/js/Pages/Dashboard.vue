<script setup>
import AuthenticatedLayout from '@/Layouts/AuthenticatedLayout.vue';
import { Head } from '@inertiajs/vue3';
import { computed } from 'vue';
import NavLink from '@/Components/NavLink.vue';

const props = defineProps({
    clients: Array,
    users: Array
})

const clientCount = computed(() => props.clients ? props.clients.length : 0);
const userCount = computed(() => props.users ? props.users.length : 0);

</script>

<template>
    <Head title="Dashboard" />

    <AuthenticatedLayout>
        <div class="py-12">
            <div class="max-w-7xl mx-auto sm:px-6 lg:px-8">
                <h2 class="font-semibold text-xl p-2 rounded-xl text-center text-gray-600 leading-tight mb-10" style="font-size: 30px;">For those who seek an exceptional home life, there is only Sotheby's International Reality</h2>
                <div class="overflow-hidden shadow-sm sm:rounded-lg text-white" style="font-size: 40px;">
                    <div class="flex flex-wrap">
                        <img width="600" class="m-1" src="https://www.bankrate.com/2020/10/02105002/What_are_real_estate_comps.jpg" alt="">
                        <img width="600" class="m-1" src="https://images.unsplash.com/photo-1582407947304-fd86f028f716?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxzZWFyY2h8Mnx8cmVhbCUyMGVzdGF0ZXxlbnwwfHwwfHx8MA%3D%3D&w=1000&q=80" alt="">
                        <img width="600" class="m-1" src="https://i0.wp.com/businessday.ng/wp-content/uploads/2021/07/luxury-residential-real-estate.png?fit=711%2C427&ssl=1" alt="">
                        <img width="600" class="m-1" src="https://isvr.acceleragent.com/usr/1464183020/CustomPages/images/Modern-Farmhouse-Exterior_-Modern-Farmhouse-Exterior-with-arched-entry_-Modern-Farmhouse-Exterior-Modern-Farmhouse-Moder.jpg" alt="">
                    </div>
                </div>
            </div>
        </div>
    </AuthenticatedLayout>
</template>
