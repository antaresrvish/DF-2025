<script setup lang="ts">
import { Menubar, MenubarMenu } from '@/components/ui/menubar'
import { Separator } from '@/components/ui/separator';
import { Input } from '@/components/ui/input'
import { RadioGroup, RadioGroupItem } from '@/components/ui/radio-group'

import {
    Card,
    CardContent,
    CardDescription,
    CardHeader,
    CardTitle,
} from '@/components/ui/card'
import { Loader2 } from 'lucide-vue-next'
import { Sheet, SheetContent, SheetDescription, SheetHeader, SheetTitle, SheetTrigger, SheetFooter } from '@/components/ui/sheet'
import { CogIcon, MagnifyingGlassIcon, LanguageIcon, AcademicCapIcon } from "@heroicons/vue/24/outline";
import { Button } from '@/components/ui/button'

// import { useColorMode } from '@vueuse/core' cofkeo
// const mode = useColorMode()
</script>

<template>
    <Menubar class="flex m-2.5 bg-[hsl(var(--border))]">
        <div class="justify-center flex-1">
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
                                <CogIcon class="h-6 w-6" />
                            </SheetTrigger>
                            <SheetContent class="overflow-y-auto h-[100 vh]">
                                <SheetHeader>
                                    <SheetTitle>Tune Search</SheetTitle>
                                    <SheetDescription>
                                        Personalize your search experience to match your knowledge and preferences.
                                    </SheetDescription>
                                </SheetHeader>
                                <Card class="mt-5">
                                    <CardHeader>
                                        <CardTitle>
                                            <span class="flex items-center">
                                                <AcademicCapIcon class="h-6 w-6 mr-2"/>
                                                Search Level
                                            </span>
                                        </CardTitle>
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
                                </Card>
                                <Card class="mt-5">
                                    <CardHeader>
                                        <CardTitle>
                                            <span class="flex items-center">
                                                <LanguageIcon class="h-6 w-6 mr-2"/>
                                                Search Language
                                            </span>
                                        </CardTitle>
                                        <CardDescription>Select the language of the subjects that you want to search
                                        </CardDescription>
                                    </CardHeader>
                                    <CardContent>
                                        <RadioGroup default-value="option-one">
                                            <div class="flex items-center space-x-2">
                                                <RadioGroupItem id="option-1" value="option-1" />
                                                <Label for="option-1">Turkish</Label>
                                            </div>

                                            <div class="flex items-center space-x-2">
                                                <RadioGroupItem id="option-2" value="option-2" />
                                                <Label for="option-2">English</Label>
                                            </div>

                                            <div class="flex items-center space-x-2">
                                                <RadioGroupItem id="option-3" value="option-3" />
                                                <Label for="option-3">Russian</Label>
                                            </div>
                                        </RadioGroup>
                                    </CardContent>
                                </Card>
                                <SheetFooter class="mt-5">
                                    <Button class="w-full">Apply</Button>
                                </SheetFooter>
                            </SheetContent>

                        </Sheet>
                    </MenubarMenu>
                </span>
            </div>
        </div>


    </Menubar>
</template>