<script setup>
import { Head, Link } from '@inertiajs/vue3';

defineProps({
    canLogin: Boolean,
    canRegister: Boolean,
    laravelVersion: String,
    phpVersion: String,
});
</script>

<template>
    <Head title="Welcome" />

    <div
        class="relative m:flex m:justify-center m:items-center min-h-screen bg-dots-darker bg-center bg-gray-100 dark:bg-dots-lighter dark:bg-gray-900 selection:bg-gray-500 selection:text-white">
        <div class="p-6 text-left z-10">
            <div class="font font-black text-white text-6xl">
                Luxury Real Estate
            </div>
            <div v-if="canLogin" class="sm:absolute sm:top-0 sm:right-0 mt-6">
                <Link v-if="$page.props.auth.user" :href="route('dashboard')"
                    class="font-semibold text-gray-600 hover:text-gray-900 dark:text-gray-400 dark:hover:text-white focus:outline focus:outline-2 focus:rounded-sm focus:outline-gray-500">
                Dashboard</Link>
                <template v-else>
                    <div class="text-right mr-11 text-2xl">
                        <Link :href="route('login')"
                            class="font-semibold text-white-900 hover:text-gray-900 dark:text-gray-400 dark:hover:text-white focus:outline focus:outline-2 focus:rounded-sm focus:outline-gray-500">
                        Log in</Link>
                        <Link v-if="canRegister" :href="route('register')"
                            class="ml-4 font-semibold text-white-900 hover:text-gray-900 dark:text-gray-400 dark:hover:text-white focus:outline focus:outline-2 focus:rounded-sm focus:outline-gray-500">
                        Register</Link>
                    </div>
                </template>
            </div>
        </div>
    </div>
</template>

<style>
.bg-dots-darker {
    background-image: url("https://myersjackson.com/wp-content/uploads/2020/06/minimal-hero-01.jpg");
    background-repeat: no-repeat;
    background-size: cover;
}

@media (prefers-color-scheme: light) {
    .dark\:bg-dots-lighter {
        background-image: url("data:image/svg+xml,%3Csvg width='30' height='30' viewBox='0 0 30 30' fill='none' xmlns='http://www.w3.org/2000/svg'%3E%3Cpath d='M1.22676 0C1.91374 0 2.45351 0.539773 2.45351 1.22676C2.45351 1.91374 1.91374 2.45351 1.22676 2.45351C0.539773 2.45351 0 1.91374 0 1.22676C0 0.539773 0.539773 0 1.22676 0Z' fill='rgba(255,255,255,0.07)'/%3E%3C/svg%3E");
    }

    .mr-10 {
        margin: auto;
    }
}
</style>
