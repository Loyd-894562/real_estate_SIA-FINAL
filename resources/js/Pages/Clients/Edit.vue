<script setup>
import AuthenticatedLayout from '@/Layouts/AuthenticatedLayout.vue';
import { Head, Link, useForm } from '@inertiajs/vue3';

const props = defineProps({
    client: Object
})

const form = useForm({
    email: props.client.email,
    property_name: props.client.property_name,
    location: props.client.location,
    size: props.client.size,
    bedrooms: props.client.bedrooms,
    price: props.client.price,
    description: props.client.description,
    pic: props.client.pic,

})

function submit() {

    if (form.price === '') {
        // If the price is empty, call the updatePrice function to calculate and set it
        updatePrice();
    }

    // Now, the form.price value should be updated with the calculated price

    form.patch('/clients/' + props.client.id)
}


</script>

<template>
    <Head title="Edit Client" />

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
                    <button style="width: 375px;" type="submit" class="bg-blue-400 text-white p-5">Update</button>
                </form>
            </div>
        </div>
    </AuthenticatedLayout>
</template>
