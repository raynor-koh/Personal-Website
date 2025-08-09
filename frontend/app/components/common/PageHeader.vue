<script setup lang="ts">
interface PageHeaderProps {
    icon: string;
    header: string;
}

const props = defineProps<PageHeaderProps>();

</script>

<template>
    <div>
      <div class="flex items-center text-white text-3xl font-semibold gap-3 mb-6">
        <UIcon :name="props.icon" class="w-8 h-8" />
        <h1>{{ props.header }}</h1>
      </div>
    </div>
</template>