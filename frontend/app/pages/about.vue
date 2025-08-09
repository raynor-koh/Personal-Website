<script setup lang="ts">
import Education from "~/components/Education.vue";
import Experiences from "~/components/Experiences.vue";
</script>

<template>
  <div class="w-full">
    <!-- Header -->
    <div class="py-6 px-8">
      <div class="flex items-center text-white text-4xl font-semibold gap-3">
        <UIcon name="material-symbols:person" class="w-8 h-8" />
        <h1>About Me</h1>
      </div>
    </div>

    <!-- Avatar + Text -->
    <UContainer class="flex flex-row items-center mt-6 px-6">
      <!-- Avatar -->
      <div class="flex-1">
        <NuxtImg
          src="/img/avatar_photo.jpg"
          class="border-4 border-white shadow-lg"
        />
      </div>

      <!-- Lorem ipsum text box -->
      <div class="flex-2">
        <div class="prose max-w-none bg-gray-800 p-6 rounded-lg">
          <p class="text-white">
            Lorem ipsum dolor sit amet, consectetur adipiscing elit. Sed do
            eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim
            ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut
            aliquip ex ea commodo consequat. Duis aute irure dolor in
            reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla
            pariatur.
          </p>
        </div>
        <div>
          <UButtonGroup orientation="horizontal">
            <UButton
              variant="subtle"
              to="https://github.com/raynor-koh"
              target="_blank"
              class="inline-flex items-center px-4 py-2"
            >
              <template #leading>
                <UIcon
                  name="mdi:github"
                  class="w-5 h-5 mr-2 fill-current text-white"
                />
              </template>
              <span class="text-lg text-white">Github</span>
            </UButton>

            <UButton
              variant="subtle"
              to="https://www.linkedin.com/in/raynorkoh/"
              target="_blank"
              class="inline-flex items-center px-4 py-2"
            >
              <template #leading>
                <UIcon
                  name="mdi:linkedin"
                  class="w-5 h-5 mr-2 fill-current text-white"
                />
              </template>
              <span class="text-lg text-white">LinkedIn</span>
            </UButton>

            <!-- TODO: Make the email not hardcoded - maybe .env variable-->
            <UButton
              variant="subtle"
              to="mailto:raynor.koh@example.com"
              class="inline-flex items-center px-4 py-2"
            >
              <template #leading>
                <UIcon
                  name="mdi:email-outline"
                  class="w-5 h-5 mr-2 fill-current text-white"
                />
              </template>
              <span class="text-lg text-white">Email</span>
            </UButton>
          </UButtonGroup>
        </div>
      </div>
    </UContainer>

    <UContainer class="grid grid-cols-2">
        <Experiences />
      <div>
        <Education />
      </div>
    </UContainer>
  </div>
</template>
