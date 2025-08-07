<script setup lang="ts">
import { ref, onMounted, onBeforeUnmount, computed } from "vue";

export interface RoleConfig {
  role: string;
  textColor: string;
}

const roles: RoleConfig[] = [
  { role: "Student", textColor: "text-[#176ced]" },
  { role: "Developer", textColor: "text-[#d9432f]" },
  { role: "Engineer", textColor: "text-[#ffb700]" },
  { role: "Builder", textColor: "text-[#009a57]" },
];
const currentRole = ref<number>(0);
const current = computed(() => roles[currentRole.value]);
let timer: ReturnType<typeof setInterval>;

onMounted(() => {
  timer = setInterval(() => {
    currentRole.value = (currentRole.value + 1) % roles.length;
  }, 4000);
});

onBeforeUnmount(() => {
  clearInterval(timer);
});
</script>

<template>
  <section
    class="relative w-full h-screen bg-cover bg-center"
    style="
      background-image: url(https://images.ctfassets.net/y2ske730sjqp/1aONibCke6niZhgPxuiilC/2c401b05a07288746ddf3bd3943fbc76/BrandAssets_Logos_01-Wordmark.jpg?w=940);
    "
  >
    <!-- dark overlay -->
    <div class="absolute inset-0 bg-black/60"></div>

    <!-- hero content -->
    <UContainer
      as="div"
      class="relative z-10 flex flex-col items-center text-center mt-24 space-y-6"
    >
      <h1 class="text-5xl font-bold">
        <transition name="role-fade" mode="out-in">
          <!-- :key ensures Vue knows when to animate -->
          <span :key="currentRole" :class="current?.textColor">{{
            current?.role
          }}</span>
        </transition>
      </h1>

      <h2 class="text-white text-3xl">
        Hey! I&apos;m
        <transition name="role-fade" mode="out-in"
          ><span
            :key="currentRole + '-raynor'"
            :class="current?.textColor"
            class="text-4xl font-bold text-left px-0 mx-0 inline-block"
          >
            Raynor
          </span></transition
        >.
      </h2>
      <h2 class="text-white text-3xl">
        I build cool things on the web and beyond.
      </h2>

      <NuxtLink to="/cliFeature">
        <UButton
          variant="subtle"
          class="bg-white h-full rounded-lg px-4 py-2 gap-2 inline-flex items-center cursor-pointer"
        >
          <template #trailing>
            <UIcon
              name="material-symbols:arrow-circle-right"
              class="w-8 h-8 align-middle"
            />
          </template>
          <span class="text-xl leading-none">Try Out a Feature</span>
        </UButton>
      </NuxtLink>
    </UContainer>
  </section>
</template>

<style scoped>
.role-fade-enter-active,
.role-fade-leave-active {
  transition: all 0.5s ease;
}

.role-fade-enter-from {
  opacity: 0;
  transform: translateY(10px) scale(0.95);
}

.role-fade-enter-to {
  opacity: 1;
  transform: translateY(0) scale(1);
}

.role-fade-leave-from {
  opacity: 1;
  transform: translateY(0) scale(1);
}

.role-fade-leave-to {
  opacity: 0;
  transform: translateY(-10px) scale(0.95);
}
</style>
