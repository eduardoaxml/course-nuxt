<template>
    <nav class="bg-white border-gray-200 dark:bg-gray-900">
        <div class="max-w-screen-xl flex flex-wrap items-center justify-between mx-auto px-4">
            <a href="/" class="flex items-center space-x-3 rtl:space-x-reverse">
                <img src="/images/logo-pab.png" class="h-16" alt="Nuxt Logo" />
            </a>
            <button data-collapse-toggle="navbar-default" type="button" class="inline-flex items-center p-2 w-10 h-10 justify-center text-sm text-gray-500 rounded-lg md:hidden hover:bg-gray-100 focus:outline-none focus:ring-2 focus:ring-gray-200 dark:text-gray-400 dark:hover:bg-gray-700 dark:focus:ring-gray-600" aria-controls="navbar-default" aria-expanded="false">
                <span class="sr-only">Open main menu</span>
                <svg class="w-5 h-5" aria-hidden="true" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 17 14">
                    <path stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M1 1h15M1 7h15M1 13h15"/>
                </svg>
            </button>
            <div class="hidden w-full md:block md:w-auto" id="navbar-default">
                <ul class="font-medium flex flex-col p-4 md:p-0 mt-4 border border-gray-700 rounded-lg bg-gray-900 md:flex-row md:space-x-8 rtl:space-x-reverse md:mt-0 md:border-0">
                    <li>
                        <NuxtLink to="/" class="block py-2 px-3 text-white bg-blue-700 rounded md:bg-transparent md:text-blue-700 md:p-0 dark:text-white md:dark:text-blue-500" aria-current="page">Home</NuxtLink>
                    </li>
                    <li>
                        <NuxtLink to="/about" class="block py-2 px-3 text-gray-900 rounded hover:bg-gray-100 md:hover:bg-transparent md:border-0 md:hover:text-blue-700 md:p-0 dark:text-white md:dark:hover:text-blue-500 dark:hover:bg-gray-700 dark:hover:text-white md:dark:hover:bg-transparent">About</NuxtLink>
                    </li>
                    <li>
                        <NuxtLink to="/iphone" class="block py-2 px-3 text-gray-900 rounded hover:bg-gray-100 md:hover:bg-transparent md:border-0 md:hover:text-blue-700 md:p-0 dark:text-white md:dark:hover:text-blue-500 dark:hover:bg-gray-700 dark:hover:text-white md:dark:hover:bg-transparent">Iphones</NuxtLink>
                    </li>
                    <li v-if="auth.isAuthenticated">
                        <NuxtLink to="/profile" class="block py-2 px-3 text-gray-900 rounded hover:bg-gray-100 md:hover:bg-transparent md:border-0 md:hover:text-blue-700 md:p-0 dark:text-white md:dark:hover:text-blue-500 dark:hover:bg-gray-700 dark:hover:text-white md:dark:hover:bg-transparent">Profile</NuxtLink>
                    </li>
                    <li v-if="auth.isAuthenticated">
                        <button class="ml-4 text-white" @click="logout">Logout</button>
                    </li>
                    <li v-else>
                        <NuxtLink to="/login" class="text-white">Login</NuxtLink>
                    </li>
                </ul>
            </div>
            <div class="text-white">
                <p class="mr-4">Cart ({{ cart.length }})</p>
                <p>Total Route Changed : {{ pageVisitCount }}</p>
            </div>
        </div>
    </nav>
</template>

<script setup>
const cart = useCart();
const auth = useAuth();
const pageVisitCount = ref(0);

onMounted(() => {
    pageVisitCount.value = usePageVisitCount();
});

function logout() {
    auth.value.isAuthenticated = false;
}
</script>