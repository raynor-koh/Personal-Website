<script setup>
import TopBar from '~/components/TopBar.vue'
import Footer from '~/components/Footer.vue'
</script>

<template>
  <div class="flex flex-col bg-black">
    <TopBar />

    <main class="flex-1">
      <slot />
    </main>

    <Footer />
  </div>
</template>
