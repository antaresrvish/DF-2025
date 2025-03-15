<script setup lang="ts">
import { SidebarProvider, SidebarTrigger } from "@/components/ui/sidebar";
import AppSidebar from "@/components/AppSidebar.vue";
import MenuBar from "@/components/MenuBar.vue";
</script>

<template>
  <MenuBar class="hidden lg:flex" />
  <SidebarProvider class="lg:hidden">
    <AppSidebar/>
    <main>
      <SidebarTrigger />
      <slot />
    </main>
  </SidebarProvider>
</template>
 