<script setup lang="ts">
import LandingPage from "~/components/LandingPage/LandingPage.vue";
import Experiences from "~/components/Experiences/Experiences.vue";
import Education from "~/components/Education/Education.vue";
</script>

<template>
  <div class="w-full h-full">
    <LandingPage />
    <div class="grid grid-cols-1">
      <Experiences />
    </div>
  </div>
</template>
