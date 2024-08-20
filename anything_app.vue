<template>
  <div>
    <ul>
      <li><a href="#" @click="view('home')">Home</a></li>
      <li><a href="#" @click="view('counter')">Counter</a></li>
    </ul>
    <NuxtPage />
    <LazyHomeWelcome v-if="page === 'home'" />
    <LazyCounter v-if="page === 'counter'" />
  </div>
</template>

<script setup>
  const page = ref("home");
  function view(name){
    page.value = name;
  }
</script>


