<template>
  <div class="w-full bg-white p-4 flex flex-col justify-between shadow rounded-lg">
    <div class="flex items-center justify-start gap-x-10">
      <div
        class="rounded-1/2 flex h-16 w-16 items-center justify-center rounded-full bg-brand"
      >
        <DashboardOrganisationIcon />
      </div>
      <div class="text-2xl font-semibold">
        <h2 class="m-2">Organisations</h2>
        <h2 class="m-2 text-4xl">{{ organisationCount }}</h2>
      </div>
    </div>

    <div class="flex w-full items-center justify-between text-xl underline">
      <h2 class="">Last updated</h2>
      <h2 class="">{{ lastUpdated }}</h2>
    </div>
  </div>
</template>

<script setup>
import DashboardOrganisationIcon from "../icons/DashboardOrganisationIcon.vue";
defineProps({
  organisationCount: {
    type: Number,
    default: 428977,
  },
  lastUpdated: {
    type: String,
    default: "20/09/2022",
  },
});
</script>

<style lang="scss" scoped></style>
