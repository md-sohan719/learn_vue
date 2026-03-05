<script setup>
// import { reactive } from 'vue';
// import { router } from '@inertiajs/vue3';
import { useForm } from '@inertiajs/vue3';

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
        <div class="mb-6">
            <label for="name" class="block text-sm font-medium leading-6 text-slate-900 first-letter:capitalize">Name</label>
            <input type="text" class="block w-full rounded-md border-0 p-2 text-slate-900 shadow-sm ring-1 ring-inset ring-slate-300 placeholder:text-slate-500 focus:ring-2 focus:ring-inset focus:ring-blue-500 sm:text-sm bg-white" v-model="form.name">
            <small class="text-red-500">{{ form.errors.name }}</small>
        </div>
        <div class="mb-6">
            <label for="email" class="block text-sm font-medium leading-6 text-slate-900">Email</label>
            <input type="email" class="block w-full rounded-md border-0 p-2 text-slate-900 shadow-sm ring-1 ring-inset ring-slate-300 placeholder:text-slate-500 focus:ring-2 focus:ring-inset focus:ring-blue-500 sm:text-sm bg-white" v-model="form.email">
            <small class="text-red-500">{{ form.errors.email }}</small>
        </div>
        <div class="mb-6">
            <label for="password" class="block text-sm font-medium leading-6 text-slate-900">Password</label>
            <input type="password" class="block w-full rounded-md border-0 p-2 text-slate-900 shadow-sm ring-1 ring-inset ring-slate-300 placeholder:text-slate-500 focus:ring-2 focus:ring-inset focus:ring-blue-500 sm:text-sm bg-white" v-model="form.password">
            <small class="text-red-500">{{ form.errors.password }}</small>
        </div>
        <div class="mb-6">
            <label for="password_confirmation" class="block text-sm font-medium leading-6 text-slate-900">Confirm Password</label>
            <input type="password" class="block w-full rounded-md border-0 p-2 text-slate-900 shadow-sm ring-1 ring-inset ring-slate-300 placeholder:text-slate-500 focus:ring-2 focus:ring-inset focus:ring-blue-500 sm:text-sm bg-white" v-model="form.password_confirmation">
            <small class="text-red-500">{{ form.errors.password_confirmation }}</small>
        </div>
        <div>
            <p class="text-sm text-slate-500">
                Already have an account? <a href="#" class="text-blue-500 hover:underline">Log in</a>
            </p>
        </div>
        <button type="submit" class="bg-indigo-600 hover:bg-indigo-700 text-white font-bold py-2 px-4 rounded" :disabled="form.processing">Register</button>
    </form>
</template>
