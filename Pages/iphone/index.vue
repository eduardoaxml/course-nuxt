<template>

    <!-- Container -->
    <div class="max-w-screen-xl mx-auto px-4">
        <!-- Grid wrapper -->
        <div class="-mx-4 flex flex-wrap">
            <!-- Grid column -->
            <div class="w-full flex flex-col p-4 sm:w-1/2 lg:w-3/12"  v-for="iphone in iphones" :key="iphone">
                <!-- Column contents -->
                <div
                    class="flex flex-col flex-1 px-10 py-12 bg-white rounded-lg shadow-lg items-center"
                >
                    <div class="flex-1 text-center">
                        <h2 class="text-gray-900 text-2xl font-bold leading-snug">
                            {{ iphone }}
                        </h2>
                        <p class="mt-2 text-lg">
                            <img width="200" :src="`/images/${iphone}.webp`" alt="" />
                        </p>
                    </div>
                    <nuxt-link
                        :to="`/iphone/${iphone}`"
                        class="mt-6 inline-flex items-center px-6 py-3 text-white font-semibold bg-blue-700 rounded-md shadow-sm"
                    >
                        {{ iphone }}
                    </nuxt-link>
                </div>
            </div>
        </div>
    </div>
</template>

<script setup>
    useHead({
        title: "Nuxt3 - Iphones",
    });

    const iphones = ["iphone-12", "iphone-12-pro", "iphone-13", "iphone-13-pro"];

    // const { data } = useFetch("/iphones");
    // const iphones = data;
</script>
