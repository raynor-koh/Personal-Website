<script setup lang="ts">
interface Education {
  university: string;
  period: string;
  description: string;
  flagIcon: string;
}

const educations: Education[] = [
  {
    university: "Zhejiang University",
    period: "Sep 2025 - Jan 2026",
    description: "Exchange Student (AY25/26 Sem 1)",
    flagIcon: "twemoji:flag-china",
  },
  {
    university: "National University of Singapore",
    period: "Aug 2023 - May 2027",
    flagIcon: "twemoji:flag-singapore",
    description: "Bachelors of Computing (Computer Science)",
  },
];
</script>

<template>
  <section class="w-full">
    <div class="space-y-8 p-0">
      <h2 class="text-white text-3xl font-bold">Education</h2>

      <div class="grid grid-cols-1 gap-6">
        <div v-for="(edu, index) in educations" :key="index"
          class="bg-white rounded-xl p-6 shadow-lg flex flex-col items-start gap-6">
          <div>
            <div class="flex items-center space-x-2">
              <div class="w-8 h-5 shrink-0">
                <UIcon :name="edu.flagIcon" class="w-full h-full" />
              </div>

              <h3 class="text-xl font-semibold text-gray-900">
                {{ edu.university }}
              </h3>
            </div>

            <p class="text-gray-600">{{ edu.description }}</p>

            <p class="text-gray-600">{{ edu.period }}</p>

          </div>
        </div>
      </div>
    </div>
  </section>
</template>
