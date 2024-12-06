<template>
  <div>
    <Header />
    <NuxtPage />
  </div>
</template>

<script setup>

import Header from "./components/Header.vue"

useHead({
  title: "My italiano recipe",
})
</script>