<script setup lang="ts">
</script>

<template>
  <nav class="top-bar flex items-center justify-between p-4 bg-black">
    <!-- Logo / Home link -->
    <NuxtLink to="/" class="font-bold text-lg text-white">
      <UIcon name="material-symbols:home-rounded" class="w-8 h-8 mr-3"/>
    </NuxtLink>

    <!-- Page links -->
    <ul class="flex space-x-4">
      <li class="text-white text-lg"><NuxtLink to="/about">About</NuxtLink></li>
      <li class="text-white text-lg"><NuxtLink to="/projects">Projects</NuxtLink></li>
      <li class="text-white text-lg"><NuxtLink to="/contact">Contact</NuxtLink></li>
    </ul>

  </nav>
</template>
