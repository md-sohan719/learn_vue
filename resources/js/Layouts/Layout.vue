<script setup>
import { Link } from '@inertiajs/vue3';
</script>
<template>
    <div>
        <header class="bg-slate-800 shadow-md">
            <nav class="p-5 max-w-screen-lg mx-auto flex items-center justify-between">
                <div class="space-x-6">
                    <Link :href="route('home')" class="text-slate-200 hover:bg-slate-700 hover:text-white rounded-md px-3 py-2 text-sm font-medium">Home</Link>
                </div>
                <div class="space-x-6">
                    <Link :href="route('register')" class="text-slate-200 hover:bg-slate-700 hover:text-white rounded-md px-3 py-2 text-sm font-medium">Register</Link>
                    <Link :href="route('login')" class="text-slate-200 hover:bg-slate-700 hover:text-white rounded-md px-3 py-2 text-sm font-medium">Login</Link>
                </div>
            </nav>
        </header>
        <main class="max-w-screen-lg mx-auto p-5">
            <slot></slot>
        </main>
    </div>
</template>
