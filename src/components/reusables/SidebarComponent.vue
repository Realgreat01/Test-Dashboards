<template>
  <div class="bar_container">
    <div class="bar_content">
      <ul>
        <li class="active" v-for="(nav, index) in sidebars" :key="index">
          <router-link :to="nav.route" class="active flex gap-x-4">
            <keep-alive>
              <component :is="nav.icon" class="fill-[#404040]"> </component>
            </keep-alive>
            <p>{{ nav.name }}</p></router-link
          >
        </li>
      </ul>
     <div class="w-[98%] flex items-center justify-start h-10">
       <ButtonComponent text="Log Out" @click="logout" :component="LogoutIcon" customStyle="height: 35px" />
     </div>
    </div>
  </div>
</template>
<script setup>
import { markRaw } from "vue";
import ButtonComponent from "./ButtonComponent.vue";
import DashboardIcon from "../icons/DashboardIcon.vue";
import UsersIcon from "../icons/UsersIcon.vue";
import NetworksIcon from "../icons/NetworksIcon.vue";
import OrganizationIcon from "../icons/OrganizationIcon.vue";
import DriversIcon from "../icons/DriversIcon.vue";
import LogoutIcon from "../icons/LogoutIcon.vue";
import { useRouter } from "vue-router";

const router = useRouter();
const sidebars = markRaw([
  { name: "Dashboard", route: "/admin/dashboard", icon: DashboardIcon },
  { name: "Users", route: "/admin/users", icon: UsersIcon },
  { name: "Networks", route: "/admin/networks", icon: NetworksIcon },
  {
    name: "Organizations",
    route: "/admin/organizations",
    icon: OrganizationIcon,
  },
  { name: "Drivers", route: "/admin/drivers", icon: DriversIcon },
]);
const logout = () => {
  localStorage.removeItem("auth-token");
  router.replace("/");
};
</script>
<style lang="scss" scoped>

.router-link-active {
  @apply font-bold text-brand;
  svg {
    @apply fill-brand;
  }
}
a {
  text-decoration: none;
  color: #404040;
  font-weight: 600;
  font-size: 14px;
}
li {
  list-style-type: none;
  width: 100%;
  padding: 20px;
}
ul {
  display: flex;
  flex-direction: column;
  /* gap: 10px; */
  justify-content: flex-start;
  align-items: flex-start;
  width: 100%;
}
.bar_content {
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  align-items: center;
  height: 90vh !important;
  padding-top: 30px;
}
</style>
