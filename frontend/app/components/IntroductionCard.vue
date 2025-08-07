<script setup lang="ts"></script>

<template>
    <UContainer
      class="flex flex-col mx-auto justify-center space-y-5 p-4 max-w-3xl bg-white rounded-2xl"
    >
      <p class="text-subtext0 text-lg leading-relaxed text-left">
        A penultimate student majoring in Computer Science at the National
        University of Singapore (NUS). I have experience in full-stack web
        development with frameworks such as Next.JS and Flask.
      </p>

      <p class="text-subtext1 text-left">
        My focus areas in university are Parallel Computing and Programming
        Languages, but in the pursuit of knowledge, I have taken other classes
        such as Database Systems, Computer Networks and AI/ML.
      </p>

      <UButtonGroup orientation="horizontal">
        <UButton
          variant="subtle"
          to="https://github.com/raynor-koh"
          target="_blank"
          class="inline-flex items-center px-4 py-2"
        >
          <template #leading>
            <UIcon name="mdi:github" class="w-5 h-5 mr-2" />
          </template>
          <span class="text-lg">Github</span>
        </UButton>

        <UButton
          variant="subtle"
          to="https://www.linkedin.com/in/raynorkoh/"
          target="_blank"
          class="inline-flex items-center px-4 py-2"
        >
          <template #leading>
            <UIcon name="mdi:linkedin" class="w-5 h-5 mr-2" />
          </template>
          <span class="text-lg">LinkedIn</span>
        </UButton>
      </UButtonGroup>
    </UContainer>
</template>
