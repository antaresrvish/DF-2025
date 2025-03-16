<script setup lang="ts">
import { SidebarProvider, SidebarTrigger } from "@/components/ui/sidebar";
import AppSidebar from "@/components/AppSidebar.vue";
import MenuBar from "@/components/MenuBar.vue";

import { ref, provide } from "vue";

const isSidebarOpen = ref(false);
const toggleSidebar = () => (isSidebarOpen.value = !isSidebarOpen.value);

provide("sidebarState", isSidebarOpen);
provide("toggleSidebar", toggleSidebar);
</script>

<template>
  
  <SidebarProvider class="">
    <AppSidebar/>
    <main>
      <SidebarTrigger class="mt-4" />
      <slot />
    </main>
    <MenuBar class="w-full mr-20 ml-5"/>
  </SidebarProvider>
</template>
 