<script setup lang="ts">
import { defineProps } from "vue";

export type ProjectStatus = "planned" | "in-progress" | "completed";

export interface Project {
  title: string;
  description: string;
  tags: string[];
  year: number;
  month: number;
  href: string;
  thumbnail?: string;
  status: ProjectStatus;
}

const props = defineProps<Project>();
</script>

<template>
  <div class="relative block bg-gray-800 rounded-lg">
    <!-- status badge in top-right -->
    <div v-if="props.status" class="absolute top-3 right-3">
      <span
        class="px-2 py-1 text-xs font-semibold text-white uppercase rounded"
        :class="{
          'bg-gray-500': props.status === 'planned',
          'bg-yellow-500': props.status === 'in-progress',
          'bg-green-500': props.status === 'completed',
        }"
      >
        {{ props.status.replace("-", " ") }}
      </span>
    </div>

    <!-- screenshot / window slot -->
    <!-- screenshot / window slot -->
    <div class="bg-gray-900 rounded-t-lg overflow-hidden">
      <div
        class="flex items-center justify-between px-4 py-2 border-b border-gray-700"
      >
        <div class="flex space-x-2">
          <span class="h-3 w-3 rounded-full bg-red-500"></span>
          <span class="h-3 w-3 rounded-full bg-yellow-500"></span>
          <span class="h-3 w-3 rounded-full bg-green-500"></span>
        </div>
      </div>

      <div class="h-40">
        <slot name="window">
          <img
            :src="props.thumbnail ?? '/img/nuxt_logo.png'"
            :alt="
              props.title ? props.title + ' thumbnail' : 'project thumbnail'
            "
            class="block w-full h-full object-cover"
            loading="lazy"
          />
        </slot>
      </div>
    </div>

    <!-- card body -->
    <div class="p-4">
      <h3 class="text-lg font-semibold text-white">{{ props.title }}</h3>
      <p class="text-gray-300 mt-2 line-clamp-3">{{ props.description }}</p>
      <div class="flex flex-row justify-between mt-4">
        <!-- tags -->
        <div class="flex flex-wrap gap-2 items-center">
          <span
            v-for="tag in tags"
            :key="tag"
            class="text-xs bg-gray-700 text-gray-200 px-2 py-1 rounded"
          >
            {{ tag }}
          </span>
        </div>
        <div>
          <NuxtLink :to="props.href" target="_blank">
            <UIcon name="mdi:github" class="text-white" :size="32" />
          </NuxtLink>
        </div>
      </div>
    </div>
  </div>
</template>
