<template>
    <p>Profile Page</p>
</template>


<script>
    definePageMeta({
        layout: "sidebar",
        middleware: ["auth"],
    });
</script>