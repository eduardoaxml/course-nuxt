<template>
    <NuxtLink to="/">Home</NuxtLink>
    <NuxtLink to="about">About</NuxtLink>

    <button @click="moveToAbout">Go to about</button>
    
    <h2>Index</h2>
    
</template>

<script setup>
    function moveToAbout() {
        navigateTo("about");
    }
</script>