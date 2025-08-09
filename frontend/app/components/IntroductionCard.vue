<script setup lang="ts"></script>

<template>
  <UContainer class="flex flex-col mx-auto justify-center space-y-5 p-4 max-w-3xl bg-white rounded-2xl">
    <p class="text-subtext0 text-lg leading-relaxed text-lef">
      Hi! I'm Raynor, a student and programmer based out of Singapore. I like to make cool projects when I'm bored. I am
      currently
      looking for software engineering internships and am open to
      relocating to overseas.
    </p>

    <p class="text-subtext1 text-left">
      This website is just a showcase of the projects I have built.
      I will try to update this site as frequently as possible.
    </p>

    <UButtonGroup orientation="horizontal">
      <UButton variant="subtle" to="https://github.com/raynor-koh" target="_blank"
        class="inline-flex items-center px-4 py-2">
        <template #leading>
          <UIcon name="mdi:github" class="w-5 h-5 mr-2" />
        </template>
        <span class="text-lg">Github</span>
      </UButton>

      <UButton variant="subtle" to="https://www.linkedin.com/in/raynorkoh/" target="_blank"
        class="inline-flex items-center px-4 py-2">
        <template #leading>
          <UIcon name="mdi:linkedin" class="w-5 h-5 mr-2" />
        </template>
        <span class="text-lg">LinkedIn</span>
      </UButton>
      <!-- TODO: Make the email not hardcoded - maybe .env variable-->
      <UButton variant="subtle" to="mailto:raynor.koh@example.com" class="inline-flex items-center px-4 py-2">
        <template #leading>
          <UIcon name="mdi:email-outline" class="w-5 h-5 mr-2" />
        </template>
        <span class="text-lg">Email</span>
      </UButton>
    </UButtonGroup>
  </UContainer>
</template>
