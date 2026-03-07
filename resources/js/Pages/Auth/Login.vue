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
    email: null,
    password: null,
    remember: null,
});

// const submit = () => {
//     router.post('/register', form);
// };
const submit = () => {
   form.post('/login', {
    onError: () => form.reset('password'),
   });
};
</script>

<template>
    <Head title=" | Login" />

    <h1 class="text-3xl font-bold">Log in to your account</h1>

    <form @submit.prevent="submit">
        <TextInput name="Email" type="email" v-model="form.email" :message="form.errors.email" />
        <TextInput name="Password" type="password" v-model="form.password" :message="form.errors.password" />

        <div class="flex items-center justify-between mb-4">
            <div class="flex items-center space-x-2">
                <label for="remember">Remember Me</label>
                <input type="checkbox" id="remember" v-model="form.remember" />
            </div>
            <p class="text-sm text-slate-500">
                    Need an account? <a :href="route('register')" class="text-blue-500 hover:underline">Register</a>
                </p>
        </div>

        <button type="submit" class="bg-indigo-600 hover:bg-indigo-700 text-white font-bold py-2 px-4 rounded" :disabled="form.processing">Login</button>
    </form>
</template>
