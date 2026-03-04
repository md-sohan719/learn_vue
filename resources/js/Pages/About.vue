<script setup>
defineProps({
    user: String
})
</script>

<template>
       <Head title=" | About" />
    <div>
        <h1> About Page </h1>
        <p>Welcome, {{ user }}!</p>
    </div>
</template>
