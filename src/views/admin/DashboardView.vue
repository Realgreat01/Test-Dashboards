<template>
  <div class="">
    <div
      class="relative mx-auto my-4 grid h-1/2 w-full gap-4"
      style="grid-template-columns: 1fr 2fr"
    >
      <DashboardOrganisations />
      <div class="grid grid-cols-2 gap-4">
        <DashboardUsers />
        <PublicNetwork />
        <PrivateNetwork />
        <DashboardDrivers />
      </div>
    </div>
    <LineChart :options="chartOptions" :series="series" />
  </div>
</template>

<script setup>
import LineChart from "@/components/admin/LineChart.vue";
import { ref } from "vue";
import DashboardOrganisations from "@/components/admin/DashboardOrganisations.vue";
import DashboardUsers from "@/components/admin/DashboardUsers.vue";
import PublicNetwork from "@/components/admin/PublicNetwork.vue";
import PrivateNetwork from "@/components/admin/PrivateNetwork.vue";
import DashboardDrivers from "@/components/admin/DashboardDrivers.vue";
const chartOptions = ref({
  chart: {
    id: "vuechart-example",
    responsive: true,
  },
  xaxis: {
    categories: [1991, 1992, 1993, 1994, 1995, 1996, 1997, 1998],
  },
});
const series = ref([
  {
    name: "series-1",
    data: [30, 40, 45, 50, 49, 60, 70, 81],
  },
]);
</script>

<style lang="scss" scoped></style>
