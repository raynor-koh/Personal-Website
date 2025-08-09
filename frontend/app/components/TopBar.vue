<script setup lang="ts">
const route = useRoute();

const displayName = computed(() => {
  if (!route.name) return ''
  const name = String(route.name)
  return name === "index" ? '' : name
})
</script>

<template>
  <nav class="top-bar flex items-center justify-between p-4 bg-black">
    <!-- Logo / Home link -->
    <span class="font-bold text-lg text-white">
      <NuxtLink to="/" class="inline-block">~/</NuxtLink>{{ displayName }}
    </span>

    <!-- Page links -->
    <ul class="flex space-x-4">
      <li class="text-white text-lg">
        <NuxtLink to="/about">About</NuxtLink>
      </li>
      <li class="text-white text-lg">
        <NuxtLink to="/projects">Projects</NuxtLink>
      </li>
    </ul>
  </nav>
</template>
