<script setup lang="ts">
import ProjectCard from "~/components/Projects/ProjectCard.vue";
import type { Project } from "~/components/Projects/ProjectCard.vue";

const projects: Project[] = [
  {
    title: "RobinBank",
    description: "Gamified Stock Trading Android App",
    tags: ["Flutter", "Dart", "Express", "Typescript"],
    year: 2024,
    month: 8,
    href: "https://github.com/raynor-koh/Orbital23-24",
    thumbnail:
      "https://i.pcmag.com/imagery/reviews/05cItXL96l4LE9n02WfDR0h-5..v1582751026.png",
    status: "completed",
  },
  {
    title: "Personal Website",
    description: "The current website you are seeing now",
    tags: ["Nuxt.js", "Typescript"],
    year: 2025,
    month: 8,
    href: "https://github.com/raynor-koh/Personal-Website",
    thumbnail: "/img/nuxt_logo.png",
    status: "in-progress",
  },
];

const sorted = computed(() =>
  [...projects].sort((a, b) => {
    const now = new Date();
    const aVal =
      (a.year ?? now.getFullYear()) * 12 + (a.month ?? now.getMonth() + 1);
    const bVal =
      (b.year ?? now.getFullYear()) * 12 + (b.month ?? now.getMonth() + 1);
    const diff = bVal - aVal;
    return diff || a.title.localeCompare(b.title);
  })
);
</script>

<template>
  <div class="bg-black">
    <div class="px-8 py-6">
      <div
        class="flex items-center text-white text-4xl font-semibold gap-3 mb-8"
      >
        <UIcon name="material-symbols:folder-copy" class="w-8 h-8" />
        <h1>Projects</h1>
      </div>

      <div
        class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 xl:grid-cols-4 gap-6"
      >
        <ProjectCard v-for="p in sorted" :key="p.title" v-bind="p" />
      </div>
    </div>
  </div>
</template>
