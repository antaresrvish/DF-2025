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
import { Separator } from '@/components/ui/separator';
import { Input } from '@/components/ui/input'
import { RadioGroup, RadioGroupItem } from '@/components/ui/radio-group'
import { Avatar, AvatarFallback, AvatarImage } from '@/components/ui/avatar'

import { CogIcon } from "@heroicons/vue/24/outline";
import { MoonIcon } from "@heroicons/vue/24/outline";
import { MagnifyingGlassIcon } from "@heroicons/vue/24/outline";
import { UserIcon } from "@heroicons/vue/24/outline";
import { AcademicCapIcon } from "@heroicons/vue/24/outline";


import { useColorMode } from '@vueuse/core'
const mode = useColorMode()
</script>

<template>
    <Menubar class="flex justify-between py-6 m-2">
        <h1
            class="duration-200 flex h-8 shrink-0 items-center rounded-md px-2 text-xs font-medium text-sidebar-foreground/70 outline-none ring-sidebar-ring transition-[margin,opa] ease-linear focus-visible:ring-2 [&>svg]:size-4 [&>svg]:shrink-0 group-data-[collapsible=icon]:-mt-8 group-data-[collapsible=icon]:opacity-0">
            DATA FORCE</h1>
        <div class="relative w-full max-w-sm items-center -ml-1">
            <Input id="search" type="text" placeholder="Search..." class="pl-10 pr-24" />
            <span class="absolute start-0 inset-y-0 flex items-center justify-center px-2">
                <MagnifyingGlassIcon class="size-6 text-muted-foreground" />
            </span>
            <span class="absolute end-0 inset-y-0 flex items-center justify-center px-2">
                <Separator orientation="vertical" class="mr-2 ml-2" />
                <MenubarMenu class="w-full h-full">
                    <MenubarTrigger class="-mr-2 -ml-2 h-full"><AcademicCapIcon class="h-5 w-6" /></MenubarTrigger>
                    <MenubarContent align="center">
                        <RadioGroup default-value="option-one">
                            <MenubarItem>
                                <div class="flex items-center space-x-2">
                                    <RadioGroupItem id="option-1" value="option-1" />
                                    <Label for="option-1">Beginner</Label>
                                </div>
                            </MenubarItem>
                            <MenubarItem>
                                <div class="flex items-center space-x-2">
                                    <RadioGroupItem id="option-2" value="option-2" />
                                    <Label for="option-2">Intermediate</Label>
                                </div>
                            </MenubarItem>
                            <MenubarItem>
                                <div class="flex items-center space-x-2">
                                    <RadioGroupItem id="option-3" value="option-3" />
                                    <Label for="option-3">Advanced</Label>
                                </div>
                            </MenubarItem>
                            <MenubarItem>
                                <div class="flex items-center space-x-2">
                                    <RadioGroupItem id="option-4" value="option-4" />
                                    <Label for="option-4">Expert</Label>
                                </div>
                            </MenubarItem>
                            <MenubarItem>
                                <div class="flex items-center space-x-2">
                                    <RadioGroupItem id="option-5" value="option-5" />
                                    <Label for="option-5">Professional</Label>
                                </div>
                            </MenubarItem>
                        </RadioGroup>
                    </MenubarContent>
                </MenubarMenu>
            </span>
        </div>
        <Menubar class="flex justify-end">
            <MenubarMenu>
                <MenubarTrigger>
                    <MoonIcon class="h-5 w-6" />
                </MenubarTrigger>
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
            <MenubarMenu>
                <MenubarTrigger>
                    <CogIcon class="h-5 w-6" />
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
                <MenubarTrigger>
                    <UserIcon class="h-5 w-6" />
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
        </Menubar>
    </Menubar>
</template>