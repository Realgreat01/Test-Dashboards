<template>
  <div class="flex flex-col justify-between gap-4">
    <div class="grid grid-cols-2 gap-x-2">
      <ProfileInfomation />
      <div class="grid grid-rows-2 gap-y-4">
        <AccountDetails />
        <ResidentialAddress />
      </div>
    </div>

    <div style="grid-template-columns: 3fr 2fr" class="grid gap-4">
      <RideHistory />
      <div class="flex flex-col gap-4">
        <div class="grid grid-cols-2 gap-4">
          <TotalRidesCount />
          <TotalCancelledRides />
          <TeamMembers />
          <TotalRideDistance />
        </div>
        <PromotionsDetails />
      </div>
    </div>
    <TableGridComponent
      :headings="headings"
      :list="users"
      route=""
      :gridRows="'grid-template-columns: 1fr 2fr 3fr 3fr 2fr 1fr'"
    />
  </div>
</template>

<script setup>
import ProfileInfomation from "@/components/admin/ProfileInfomation.vue";
import AccountDetails from "@/components/admin/AccountDetails.vue";
import ResidentialAddress from "@/components/admin/ResidentialAddress.vue";
import RideHistory from "@/components/admin/RideHistory.vue";
import TotalRidesCount from "@/components/admin/TotalRidesCount.vue";
import TotalCancelledRides from "@/components/admin/TotalCancelledRides.vue";
import TeamMembers from "@/components/admin/TeamMembers.vue";
import TotalRideDistance from "@/components/admin/TotalRideDistance.vue";
import PromotionsDetails from "@/components/admin/PromotionsDetails.vue";
import TableGridComponent from "@/components/admin/TableGridComponent.vue";

import axios from "axios";
import { ref, onMounted } from "vue";
import { useRouter } from "vue-router";

const route = useRouter();
const users = ref([]);
const headings = ref(["name", "email", "location", "insurance", "..."]);
onMounted(async () => {
  const { data } = await axios.get(
    import.meta.env.VITE_API_URL + "userprofiles"
  );
  console.log(data.data[0]);
  if (data) users.value = data.data;
  console.log(route);
});
</script>

<style lang="scss" scoped></style>
