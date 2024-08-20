<template>
    <p>Profile Page</p>
</template>


<script>
    definePageMeta({
        layout: "sidebar",
        middleware: ["auth"],
    });
</script>

<!-- <script>
definePageMeta({
    layout: 'default',
})


</script> -->

<!-- <script>
    definePageMeta({
        layout: false,
    });
</script> -->