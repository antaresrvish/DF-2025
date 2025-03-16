<script setup lang="ts">
import { SidebarProvider, SidebarTrigger } from "@/components/ui/sidebar";
import AppSidebar from "@/components/AppSidebar.vue";
import MenuBar from "@/components/MenuBar.vue";

</script>

<template>
    <SidebarProvider class="">
        <AppSidebar />
        <main>
            <SidebarTrigger class="mt-4" />
            <slot />
        </main>
        <MenuBar class="w-full mr-12 ml-5" />
    </SidebarProvider>
</template>