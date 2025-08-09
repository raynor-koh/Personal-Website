<script setup>
import TopBar from '~/components/TopBar.vue'
import Footer from '~/components/Footer.vue'
</script>

<template>
  <div class="flex flex-col bg-black min-h-screen">
    <TopBar />

    <main class="flex-1">
      <div class="max-w-6xl mx-auto px-4 sm:px-6 lg:px-8 py-2">
        <slot />
      </div>
    </main>

    <Footer />
  </div>
</template>
