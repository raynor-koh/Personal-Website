<script setup>
import TopBar from '~/components/TopBar/TopBar.vue'
</script>

<template>
  <div class="min-h-screen flex flex-col">
    <TopBar />

    <main class="flex-1">
      <slot />
    </main>
  </div>
</template>
