<script setup lang="ts">
interface Experience {
  company: string;
  role: string;
  period: string;
  description: string;
  technologies: string[];
  flagIcon: string;
  detailsLink: string;
}

const experiences: Experience[] = [
  {
    company: "FLING.AI",
    role: "Full-stack Software Engineering Intern",
    period: "Dec 2024 – Aug 2025",
    description: "Built AI-powered warehouse stock-checking tools",
    technologies: [
      "Next.js",
      "TailwindCSS",
      "TypeScript",
      "Flask",
      "Python",
      "Nginx",
      "Docker",
      "AWS",
    ],
    flagIcon: "twemoji:flag-thailand",
    detailsLink: "https://www.flingai.com/",
  },
  {
    company: "LiftAuth LLP",
    role: "Software Developer Intern",
    period: "May 2024 – Aug 2024",
    description: "Developed accessibility features for robotic elevators",
    technologies: ["React", "Node.js", "Firebase", "Docker", "C/C++"],
    flagIcon: "twemoji:flag-singapore",
    detailsLink: "https://liftauth.com/",
  },
  {
    company: "DSO National Laboratories",
    role: "Intern",
    period: "Jan 2023 – Mar 2023",
    description: "Analysed data for model validation",
    technologies: ["Python", "Pandas", "Arduino"],
    flagIcon: "twemoji:flag-singapore",
    detailsLink: "https://www.dso.org.sg/",
  },
];
</script>

<template>
  <section class="w-full py-12">
    <UContainer class="space-y-8">
      <h2 class="text-white text-3xl font-bold">Experiences</h2>

      <div class="grid grid-cols-1 gap-6">
        <div
          v-for="(exp, idx) in experiences"
          :key="idx"
          class="bg-white rounded-xl p-6 shadow-lg flex flex-col items-start gap-6 max-w-xl"
        >
          <div class="flex-1 flex flex-col space-y-4 w-full">
            <div class="flex items-center justify-between">
              <div class="flex items-center space-x-2">
                <UIcon :name="exp.flagIcon" class="w-6 h-6" />
                <h3 class="text-xl font-semibold text-gray-900">
                  {{ exp.role }}
                </h3>
              </div>
              <NuxtLink :to="exp.detailsLink" target="_blank">
                <UButton variant="outline" size="sm" #trailing class="gap-2 cursor-pointer"
                  ><span>Learn More</span>
                  <UIcon name="cuida:open-in-new-tab-outline"
                /></UButton>
              </NuxtLink>
            </div>

            <p class="text-gray-600 font-bold">{{ exp.company }}</p>
            <p class="text-gray-600">{{ exp.period }}</p>

            <p class="text-gray-700 leading-relaxed">{{ exp.description }}</p>

            <div class="flex flex-wrap gap-2">
              <span
                v-for="tech in exp.technologies"
                :key="tech"
                class="px-3 py-1 text-sm rounded-full bg-gray-100 text-gray-800"
              >
                {{ tech }}
              </span>
            </div>
          </div>
        </div>
      </div>
    </UContainer>
  </section>
</template>
