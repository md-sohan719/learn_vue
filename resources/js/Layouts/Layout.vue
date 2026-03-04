<script setup>
import { Link, Head } from '@inertiajs/vue3';
</script>
<template>
    <Head>
        <title>My Inertia App</title>
        <meta name="description" content="A simple Inertia.js application with Vue 3" />
    </Head>
    <div>
        <header class="bg-indigo-500 text-white">
            <nav class="flex items-center justify-between p-4 max-w-screen-lg mx-auto">
                <div class="space-x-6">
                    <Link href="/">Home</Link>
                    <Link href="/about">About</Link>
                </div>
            </nav>
        </header>
        <main>
            <slot></slot>
        </main>
    </div>
</template>
