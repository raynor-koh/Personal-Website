<script setup lang="ts">
import ProjectCard from "~/components/Projects/ProjectCard.vue";
import type { Project } from "~/components/Projects/ProjectCard.vue";
import PageHeader from "~/components/common/PageHeader.vue";

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
  {
    title: "Update Outdated Applications",
    description: "Update the outdated mobile and desktop applications",
    tags: ["React Native", "Python"],
    year: 2025,
    month: 9,
    href: "https://github.com/raynor-koh/Reverse-Engineer-Day-Code-App",
    thumbnail: "/img/reverse_engineer.png",
    status: "completed",
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
    <PageHeader icon="material-symbols:folder-copy" header="Projects" />

    <div
      class="grid grid-cols-1 sm:grid-cols-2 xl:grid-cols-3 2xl:grid-cols-4 gap-6"
    >
      <ProjectCard v-for="p in sorted" :key="p.title" v-bind="p" />
    </div>
  </div>
</template>
