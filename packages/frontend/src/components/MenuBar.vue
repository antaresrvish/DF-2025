<script setup lang="ts">
import {
    Menubar,
    MenubarContent,
    MenubarItem,
    MenubarMenu,
    MenubarSeparator,
    MenubarShortcut,
    MenubarTrigger,
} from '@/components/ui/menubar'
import { CogIcon } from "@heroicons/vue/24/outline";
import { useColorMode } from '@vueuse/core'
const mode = useColorMode()
</script>

<template>
    <Menubar class="flex justify-between py-6">
        <Menubar>

        </Menubar>
        <Menubar class="flex justify-end">
            <MenubarMenu>
                <MenubarTrigger>seciye</MenubarTrigger>
                <MenubarContent>
                    <MenubarItem>
                        New Tab <MenubarShortcut>⌘T</MenubarShortcut>
                    </MenubarItem>
                    <MenubarItem>New Window</MenubarItem>
                    <MenubarSeparator />
                    <MenubarItem>Share</MenubarItem>
                    <MenubarSeparator />
                    <MenubarItem>Print</MenubarItem>
                </MenubarContent>
            </MenubarMenu>
            <MenubarMenu>
                <MenubarTrigger>
                    <CogIcon class="h-6 w-6" />
                </MenubarTrigger>
                <MenubarContent>
                    <MenubarItem>
                        New Tab
                    </MenubarItem>
                    <MenubarItem>New Window</MenubarItem>
                    <MenubarSeparator />
                    <MenubarItem>Share</MenubarItem>
                    <MenubarSeparator />
                    <MenubarItem>Print</MenubarItem>
                </MenubarContent>
            </MenubarMenu>
            <MenubarMenu>
                <MenubarTrigger>COLOR</MenubarTrigger>
                <MenubarContent>
                    <MenubarItem @click="mode = 'light'">
                        Light
                    </MenubarItem>
                    <MenubarItem @click="mode = 'dark'">
                        Dark
                    </MenubarItem>
                    <MenubarItem @click="mode = 'auto'">
                        System
                    </MenubarItem>
                </MenubarContent>
            </MenubarMenu>

        </Menubar>

    </Menubar>
</template>