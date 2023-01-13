<template>
  <div
    class="flex h-fit w-full flex-col justify-start rounded bg-white p-3 font-semibold"
  >
    <div class="w-fit rounded-lg bg-orange-100 p-4"><TeamMembersIcon /></div>
    <h2 class="my-10 text-xl font-semibold">Team Members</h2>
    <h2 class="text-xl">
      <span class="text-3xl">{{ teamMembers }}</span> Members
    </h2>
  </div>
</template>

<script setup>
import TeamMembersIcon from "../icons/TeamMembersIcon.vue";
defineProps({
  teamMembers: {
    type: Number,
    default: 86,
  },
});
</script>

<style lang="scss" scoped></style>
