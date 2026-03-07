<script setup>
// import { reactive } from 'vue';
// import { router } from '@inertiajs/vue3';
import { useForm } from '@inertiajs/vue3';

import TextInput from '../Components/TextInput.vue';

// const form = reactive({
//     name: null,
//     email: null,
//     password: null,
//     password_confirmation: null,
// });

const form = useForm({
    name: null,
    email: null,
    password: null,
    password_confirmation: null,
});

// const submit = () => {
//     router.post('/register', form);
// };
const submit = () => {
   form.post('/register', {
    onError: () => form.reset('password', 'password_confirmation'),
   });
};
</script>

<template>
    <Head title=" | Register" />

    <h1 class="text-3xl font-bold">Register a new account</h1>

    <form @submit.prevent="submit">
       <TextInput name="Name" v-model="form.name" :message="form.errors.name" />
        <TextInput name="Email" type="email" v-model="form.email" :message="form.errors.email" />
        <TextInput name="Password" type="password" v-model="form.password" :message="form.errors.password" />
        <TextInput name="confirm password" type="password" v-model="form.password_confirmation" />

        <div>
            <p class="text-sm text-slate-500">
                Already have an account? <a href="#" class="text-blue-500 hover:underline">Log in</a>
            </p>
        </div>
        <button type="submit" class="bg-indigo-600 hover:bg-indigo-700 text-white font-bold py-2 px-4 rounded" :disabled="form.processing">Register</button>
    </form>
</template>
