<script setup></script>
<template>
    <Head :title="` | ${$page.component}`" />
    <h1 class="text-3xl font-bold text-center mt-10"> {{ $page.props.auth.user }} </h1>
</template>
