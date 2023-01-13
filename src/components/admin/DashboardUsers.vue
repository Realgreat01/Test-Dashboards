<template>
  <div class="w-full bg-white p-4 shadow rounded-lg">
    <div class="flex items-center justify-start gap-x-20">
      <div
        class="rounded-1/2 flex h-16 w-16 items-center justify-center rounded-full bg-brand"
      >
        <DashboardUserIcon />
      </div>
      <div class="text-xl font-semibold">
        <h2 class="m-2">Users</h2>
        <h2 class="m-2 text-2xl">{{ usersCount }}</h2>
      </div>
    </div>
  </div>
</template>

<script setup>
import DashboardUserIcon from '../icons/DashboardUserIcon.vue';
defineProps({
    usersCount: {
        type: Number,
        default: 747,
    }
});
</script>

<style lang="scss" scoped></style>
