<script setup lang="ts">
</script>

<template>
  <nav class="top-bar flex items-center justify-between p-4 bg-black">
    <!-- Logo / Home link -->
    <NuxtLink to="/" class="font-bold text-lg text-white">
      My Site
    </NuxtLink>

    <!-- Page links -->
    <ul class="flex space-x-4">
      <li class="text-white"><NuxtLink to="/about">About</NuxtLink></li>
      <li class="text-white"><NuxtLink to="/projects">Projects</NuxtLink></li>
      <li class="text-white"><NuxtLink to="/contact">Contact</NuxtLink></li>
    </ul>

  </nav>
</template>
