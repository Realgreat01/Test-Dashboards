<template>
  <div class="flex flex-col justify-start bg-white p-4">
    <div class="flex items-center justify-between p-4">
      <h2 class="mb-4 text-xl font-bold">Ride History</h2>
    </div>

    <div class="w-full">
      <div
        class="relative my-4 bg-brand-light p-4 text-xl font-semibold"
        v-for="(rides, index) in rideHistory"
        :key="index"
      >
        <!-- First Column  -->
        <div class="mb-6 flex justify-between">
          <div class="flex items-center gap-x-4">
            <DownLocationIcon />
            <p>{{ rides.start }}</p>
          </div>
          <div class="flex w-32 items-center justify-start gap-x-3">
            <CarIcon />
            <p>{{ rides.carModel }}</p>
          </div>
        </div>
        <!-- Long Vertical Lines -->
        <div class="absolute top-8 m-0 ml-2 h-12 w-[1px] bg-brand-dark"></div>
        <!-- Down Column of the div -->
        <div class="flex justify-between">
          <div class="flex items-center gap-x-4">
            <DownLocationIcon />
            <p>{{ rides.end }}</p>
          </div>
          <div class="bg flex w-32 items-center justify-start gap-x-3">
            <DestinationIcon />
            <p>{{ rides.distance }} km</p>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
<script setup>
import DownLocationIcon from "../icons/DownLocationIcon.vue";
import CarIcon from "../icons/CarIcon.vue";
import DestinationIcon from "../icons/DestinationIcon.vue";
import { ref } from "vue";
const rideHistory = ref([
  {
    start: "Owerri",
    end: "Lokoja",
    distance: "400",
    carModel: "Volvo",
  },
  {
    start: "Kaduna",
    end: "Kano",
    distance: "284",
    carModel: "Mercedes",
  },
  {
    start: "Abuja",
    end: "Lagos",
    distance: "20470",
    carModel: "Tesla",
  },
]);
</script>
