<template>
  <div>
    <VueApexCharts :options="options" :series="series" type="area"/>
  </div>
</template>

<script setup>
import VueApexCharts from "vue3-apexcharts";
defineProps({
  options: {
    type: Object,
  },
  series: {
    type: Object,
  },
});
</script>

<style lang="scss" scoped></style>
