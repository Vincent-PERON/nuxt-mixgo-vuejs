<template>
  <v-app>
    <v-layout>
      <v-navigation-drawer
        v-model="drawer"
        class="bg-sidebar"
        theme="dark"
        permanent
      >
        <v-list density="compact" item-props nav>
          <v-list-subheader class="sidebar-title"
            >ADMINISTRATION</v-list-subheader
          >
          <v-list-item
            v-for="i in items"
            class="item-sidebar"
            :key="i.title"
            :title="i.title"
            :prepend-icon="i.prependIcon"
            @click="navigateToPage(i.url)"
          />
        </v-list>
      </v-navigation-drawer>
    </v-layout> </v-app
  >>
</template>

<script setup lang="ts">
import { ref, onMounted } from "vue";

const drawer = ref(true);

const items = ref([
  {
    title: "Dashboard",
    prependIcon: "mdi-view-dashboard-outline",
    link: true,
    url: "/",
  },
  {
    title: "go://",
    prependIcon: "mdi-bookmark",
    link: true,
    url: "/administration/shortcuts",
  },
]);

const navigateToPage = async (page: any) => {
  await navigateTo(page);
};
</script>

<style scoped>
.bg-sidebar {
  background-color: #0f1e2c;
}

.item-sidebar {
  font-weight: bold;
  font-size: 1.5rem;
}

.sidebar-title {
  padding: 10px 0px 30px 0px;
}
</style>
