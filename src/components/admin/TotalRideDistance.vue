<template>
  <div
    class="flex h-fit w-full flex-col justify-start rounded bg-white p-3 font-semibold"
  >
    <div class="w-fit rounded-lg bg-blue-100 p-4"><RideDistanceIcon /></div>
    <h2 class="my-10 text-xl font-semibold">Total Ride Distance</h2>
    <h2 class="text-xl">
      <span class="text-3xl">{{ rideDistance }}</span> km
    </h2>
  </div>
</template>

<script setup>
import RideDistanceIcon from "../icons/RideDistanceIcon.vue";
defineProps({
  rideDistance: {
    type: Number,
    default: 86,
  },
});
</script>

<style lang="scss" scoped></style>
