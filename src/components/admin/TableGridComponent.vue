<template>
  <div class="relative w-full overflow-x-hidden">
    <div
      :style="gridRows"
      class="bold absolute grid w-full items-center justify-center bg-white p-4 text-2xl uppercase"
    >
      <input
        type="checkbox"
        name=""
        id=""
        class="h-8 w-8 border-brand-light text-4xl text-brand-dark focus:border-none focus:outline-none"
      />
      <p
        v-for="(head, index) in headings"
        :key="index"
        class="flex items-center text-xl font-semibold"
      >
        <span class="block"> {{ head }}</span>
        <span class="material-icons block" v-if="index !== headings.length - 1"
          >arrow_drop_down</span
        >
      </p>
    </div>

    <div class="mt-20">
      <RouterLink
        :to="{ name: route, params: { id: item.id || item.user_id} }"
        :style="gridRows"
        class="main-grid my-2 grid items-center justify-center p-4 px-4 text-left text-xl text-brand-dark"
        v-for="(item, index) in list"
        :key="index"
        :class="index % 2 === 0 ? 'bg-brand-light' : 'bg-white'"
      >
        <input
          type="checkbox"
          name=""
          id=""
          checked
          class="h-8 w-8 text-brand-dark"
        />
        <p>Kingsley Jane</p>
        <p>{{ item.email }}</p>
        <p>78, HighGround Street, Bouston</p>
        <p>{{ item.phone_number }}</p>
        <p>...</p>
      </RouterLink>
    </div>
  </div>
</template>

<script setup>
defineProps({
  headings: {
    type: Object,
  },
  list: {
    type: Object,
  },
  gridRows: {
    type: String,
  },
  route: {
    type: String,
    default: "users",
  },
});
</script>

<style lang="scss" scoped></style>
