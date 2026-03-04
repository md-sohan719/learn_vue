<script setup>
defineProps({
    user: String
})
</script>

<template>
    <div>
        <h1> About Page </h1>
        <p>Welcome, {{ user }}!</p>
    </div>
</template>
