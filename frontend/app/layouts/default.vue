<script setup>
import TopBar from '~/components/TopBar/TopBar.vue'
import Footer from '~/components/Footer/Footer.vue'
</script>

<template>
  <div class="min-h-lvw flex flex-col bg-black">
    <TopBar />

    <main class="flex-1">
      <slot />
    </main>

    <Footer />
  </div>
</template>
