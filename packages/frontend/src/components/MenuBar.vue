<script setup lang="ts">
import { Menubar, MenubarContent, MenubarItem, MenubarMenu, MenubarSeparator, MenubarTrigger } from '@/components/ui/menubar'
import { Separator } from '@/components/ui/separator';
import { Input } from '@/components/ui/input'
import { RadioGroup, RadioGroupItem } from '@/components/ui/radio-group'
import {
    Card,
    CardContent,
    CardDescription,
    CardFooter,
    CardHeader,
    CardTitle,
} from '@/components/ui/card'
import { Loader2 } from 'lucide-vue-next'
import { Sheet, SheetContent, SheetDescription, SheetHeader, SheetTitle, SheetTrigger } from '@/components/ui/sheet'
import { CogIcon, MoonIcon, MagnifyingGlassIcon, UserIcon, LanguageIcon } from "@heroicons/vue/24/outline";
import { Button } from '@/components/ui/button'
import {
  Tooltip,
  TooltipContent,
  TooltipProvider,
  TooltipTrigger
} from '@/components/ui/tooltip'

import { useColorMode } from '@vueuse/core'
const mode = useColorMode()
</script>

<template>
    <Menubar class="flex py-6 m-2 bg-[hsl(var(--border))]">
        <div class="justify-center flex-1 ml-1">
            <div class="relative w-full items-center">
                <Input id="search" type="text" placeholder="Search..." class="pl-10 pr-12 w-full" />
                <span class="absolute start-0 inset-y-0 flex items-center justify-center px-2">
                    <MagnifyingGlassIcon class="size-6 text-muted-foreground" />
                    <Loader2 class="animate-spin" hidden />
                </span>
                <span class="absolute end-0 inset-y-0 flex items-center justify-center px-2">
                    <Separator orientation="vertical" class="mr-2 ml-2" />
                    <MenubarMenu class="w-full h-full">
                        <Sheet>
                            <SheetTrigger>
                                <TooltipProvider>
                                    <Tooltip>
                                        <TooltipTrigger class="flex items-center justify-center">
                                            <CogIcon class="h-6 w-6" />
                                        </TooltipTrigger>
                                        <TooltipContent>
                                            <p>Tune your search experience</p>
                                        </TooltipContent>
                                    </Tooltip>
                                </TooltipProvider>
                            </SheetTrigger>
                            <SheetContent>
                                <SheetHeader>
                                    <SheetTitle>Tune Search</SheetTitle>
                                    <SheetDescription>
                                        Personalize your search experience to match your knowledge and preferences.
                                    </SheetDescription>
                                </SheetHeader>
                                <Card class="mt-5">
                                    <CardHeader>
                                        <CardTitle>Search Level</CardTitle>
                                        <CardDescription>Select the level of the subjects that you want to search
                                        </CardDescription>
                                    </CardHeader>
                                    <CardContent>
                                        <RadioGroup default-value="option-one">
                                            <div class="flex items-center space-x-2">
                                                <RadioGroupItem id="option-1" value="option-1" />
                                                <Label for="option-1">Beginner</Label>
                                            </div>

                                            <div class="flex items-center space-x-2">
                                                <RadioGroupItem id="option-2" value="option-2" />
                                                <Label for="option-2">Intermediate</Label>
                                            </div>

                                            <div class="flex items-center space-x-2">
                                                <RadioGroupItem id="option-3" value="option-3" />
                                                <Label for="option-3">Advanced</Label>
                                            </div>

                                            <div class="flex items-center space-x-2">
                                                <RadioGroupItem id="option-4" value="option-4" />
                                                <Label for="option-4">Expert</Label>
                                            </div>

                                            <div class="flex items-center space-x-2">
                                                <RadioGroupItem id="option-5" value="option-5" />
                                                <Label for="option-5">Professional</Label>
                                            </div>

                                        </RadioGroup>
                                    </CardContent>
                                    <CardFooter>
                                        <Button>Ok</Button>
                                    </CardFooter>
                                </Card>
                            </SheetContent>
                        </Sheet>
                    </MenubarMenu>
                </span>
            </div>
        </div>
        <div class="items-center justify-end hidden">
            <Menubar class="flex justify-end mr-1">
                <MenubarMenu>
                    <MenubarTrigger>
                        <MoonIcon class="h-5 w-6" />
                    </MenubarTrigger>
                    <MenubarContent align="center">
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
                        <LanguageIcon class="h-5 w-6" />
                    </MenubarTrigger>
                    <MenubarContent align="center">
                        <MenubarItem>
                            English
                        </MenubarItem>
                        <MenubarItem>
                            Turkish
                        </MenubarItem>
                    </MenubarContent>
                </MenubarMenu>
                <MenubarMenu>
                    <MenubarTrigger>
                        <CogIcon class="h-5 w-6" />
                    </MenubarTrigger>
                    <MenubarContent align="center">
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
                    <MenubarContent align="center">
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
        </div>

    </Menubar>
</template>