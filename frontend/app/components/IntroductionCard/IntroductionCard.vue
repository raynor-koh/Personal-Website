<script setup lang="ts">
</script>

<template>
    <UContainer class="flex flex-col mx-auto justify-center space-y-5 px-4 max-w-3xl bg-white">

        <h2 class="text-black text-left text-4xl">Hey! <span>I'm Raynor Koh.</span></h2>
        <p class="text-subtext0 text-lg leading-relaxed">A penultimate student majoring in Computer Science at the
            National University of Singapore (NUS). I have experience in full-stack web development with
            frameworks such as Next.JS and Flask.</p>

        <p>My focus areas in university are Parallel Computing and Programming Languages, but in the pursuit of
            knowledge, I have taken other classes such as Database Systems, Computer Networks and AI/ML.</p>

        <UButtonGroup orientation="horizontal">
            <UButton variant="subtle" to="https://github.com/raynor-koh" target="_blank"
                class="inline-flex items-center px-4 py-2">
                <template #leading>
                    <UIcon name="mdi:github" class="w-6 h-6 mr-2" />
                </template>
                <span class="text-lg">Github</span>
            </UButton>

            <UButton variant="subtle" to="https://www.linkedin.com/in/raynorkoh/" target="_blank"
                class="inline-flex items-center px-4 py-2">
                <template #leading>
                    <UIcon name="mdi:linkedin" class="w-6 h-6 mr-2" />
                </template>
                <span class="text-lg">LinkedIn</span>
            </UButton>
        </UButtonGroup>

    </UContainer>
</template>
