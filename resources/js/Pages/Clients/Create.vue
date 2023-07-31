<script setup>
import AuthenticatedLayout from '@/Layouts/AuthenticatedLayout.vue';
import { Head, Link, useForm } from '@inertiajs/vue3';

const form = useForm({
    email: '',
    property_name: '',
    location: '',
    size: '',
    bedrooms: '',
    price: '',
    description: '',
    pic: null
});

function submit() {

    form.post('/clients/');
}

</script>

<template>
    <Head title="Create Client" />
    <AuthenticatedLayout>
        <div style="display: grid; place-content: center;">
            <div style="width: 550px; margin-top: 50px; display: grid; place-content: center;" class="bg-blue-900 p-5">
                <form @submit.prevent="submit">
                    <div class="text-white">
                        <input style="width: 375px;" placeholder="Property Name" required type="text" id="property_name" v-model="form.property_name" class="text-black mb-10">
                    </div>
                    <div class="text-white">
                        <input style="width: 375px;" placeholder="Email" required type="email" id="email" v-model="form.email" class="text-black mb-10">
                    </div>
                    <div class="text-white">
                        <input style="width: 375px;" placeholder="Location" required type="text" id="location" v-model="form.location" class="text-black mb-10">
                    </div>
                    <div class="text-white">
                        <input style="width: 375px;" placeholder="Size" required type="text" id="size" v-model="form.size" class="text-black mb-10">
                    </div>
                    <div class="text-white">
                        <input style="width: 375px;" placeholder="Bedrooms" required type="text" id="bedrooms" v-model="form.bedrooms" class="text-black mb-10">
                    </div>
                    <div class="text-white">
                        <input style="width: 375px;" placeholder="Price" required type="number" id="price" v-model="form.price" class="text-black mb-10">
                    </div>
                    <div class="text-white">
                        <input style="width: 375px;" placeholder="Description" required type="text" id="description" v-model="form.description" class="text-black mb-10">
                    </div>
                    <div class="form-field text-black">
                                    <label for="pic">Cover Picture</label>
                                    <input required type="file" @input="form.pic = $event.target.files[0]" class="h-full border-gray-400 rounded text-center" accept="image/png" />
                                    <progress v-if="form.progress" :value="form.progress.percentage" max="100">
                                        {{ form.progress.percentage }}%
                                    </progress>
                                </div>
                    <button style="width: 375px;" type="submit" class="bg-blue-400 text-white p-5">Create</button>
                </form>
            </div>
        </div>
    </AuthenticatedLayout>
</template>
