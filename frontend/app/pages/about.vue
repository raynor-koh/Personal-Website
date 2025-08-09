<script setup lang="ts">
import Education from "~/components/Education.vue";
import Experiences from "~/components/Experiences.vue";
import PageHeader from "~/components/common/PageHeader.vue";

const date = ref(Date.now());
onMounted(() => {
  const interval = setInterval(() => {
    date.value = Date.now();
  }, 1000);
  onUnmounted(() => clearInterval(interval));
});

const timezone: string = "Asia/Singapore";
const location: string = "Singapore";
const locationTime: string = "SGT"
</script>

<template>
  <div class="w-full">
    <PageHeader icon="material-symbols:person" header="About Me" />

    <UContainer>
      <div class="grid grid-cols-1 md:grid-cols-2 items-stretch gap-2">
        <div class="flex items-center justify-center bg-slate-800 rounded-lg p-4">
          <NuxtImg src="/img/avatar_photo.jpg" class="border-4 border-white shadow-lg max-h-full object-contain" />
        </div>

        <div class="flex flex-col bg-slate-800 rounded-lg p-6">
          <div class="prose p-6 text-white">
            <p class="text-subtext0 text-lg leading-relaxed text-lef">
              A penultimate student majoring in Computer Science at the National
              University of Singapore (NUS). I have experience in full-stack web
              development with frameworks such as Next.JS and Flask.
            </p>

            <p class="text-subtext1 text-left">
              My focus areas in university are Parallel Computing and Programming
              Languages, but in the pursuit of knowledge, I have taken other classes
              such as Database Systems, Computer Networks and AI/ML.
            </p>
            <!-- <p class="text-red-400">
            I am a Singaporean so it is easier to get the necessary visas to
            work overseas.
          </p> -->
          </div>
          <div class="mt-auto pt-4 flex flex-col lg:flex-row items-center justify-between gap-4">
            <UButtonGroup orientation="horizontal">
              <UButton variant="subtle" to="https://github.com/raynor-koh" target="_blank"
                class="inline-flex items-center px-4 py-2">
                <template #leading>
                  <UIcon name="mdi:github" class="w-5 h-5 mr-2 fill-current text-white" />
                </template>
                <span class="text-lg text-white">Github</span>
              </UButton>

              <UButton variant="subtle" to="https://www.linkedin.com/in/raynorkoh/" target="_blank"
                class="inline-flex items-center px-4 py-2">
                <template #leading>
                  <UIcon name="mdi:linkedin" class="w-5 h-5 mr-2 fill-current text-white" />
                </template>
                <span class="text-lg text-white">LinkedIn</span>
              </UButton>

              <!-- TODO: Make the email not hardcoded - maybe .env variable-->
              <UButton variant="subtle" to="mailto:raynor.koh@example.com" class="inline-flex items-center px-4 py-2">
                <template #leading>
                  <UIcon name="mdi:email-outline" class="w-5 h-5 mr-2 fill-current text-white" />
                </template>
                <span class="text-lg text-white">Email</span>
              </UButton>
            </UButtonGroup>
            <span class="text-white text-lg whitespace-nowrap">
              {{ locationTime }}:
              <NuxtTime :datetime="date" hour="2-digit" minute="2-digit" second="numeric" hour-cycle="h23"
                :time-zone="timezone" />
            </span>

          </div>
        </div>
      </div>

      <div class="grid grid-cols-1 py-2 gap-2 md:grid-cols-2 justify-items-center">
        <Experiences />
        <Education />
      </div>
    </UContainer>
  </div>
</template>
