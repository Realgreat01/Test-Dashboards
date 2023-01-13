<template>
  <div class="relative h-full w-full">
    <TableGridComponent
      :headings="headings"
      :list="users"
      route="users"
      :gridRows="'grid-template-columns: 1fr 2fr 3fr 3fr 2fr 1fr'"
    />
  </div>
</template>

<script setup>
import axios from "axios";
import { ref, onMounted } from "vue";
import { useRouter } from "vue-router";
import TableGridComponent from "./TableGridComponent.vue";
const route = useRouter();
const users = ref([]);
const headings = ref(["name", "email", "location", "phone", "..."]);
onMounted(async () => {
  const { data } = await axios.get(import.meta.env.VITE_API_URL + "users");
  console.log(data.data[0]);
  if (data) users.value = data.data;
  console.log(route);
});
</script>

<style scoped>
.main-grid {
  grid-template-columns: 1fr 2fr 3fr 3fr 2fr 1fr;
}
</style>
