<template>
  <div>
    <TableGridComponent
      :headings="headings"
      :list="users"
      route="organisation"
      :gridRows="'grid-template-columns: 1fr 2fr 3fr 3fr 2fr 1fr'"
    />
  </div>
</template>

<script setup>
import axios from "axios";
import { ref, onMounted } from "vue";
import { useRouter } from "vue-router";

import TableGridComponent from "@/components/admin/TableGridComponent.vue";

const route = useRouter();
const users = ref([]);
const headings = ref(["name", "email", "location", "insurance", "..."]);
onMounted(async () => {
  const { data } = await axios.get(
    import.meta.env.VITE_API_URL + "networkusers"
  );
  console.log(data.data[0]);
  if (data) users.value = data.data;
  console.log(route);
});
</script>

<style lang="scss" scoped></style>
