<script setup lang="ts">
import { Button } from '@/components/ui/button'
import { useColorMode } from '@vueuse/core'
import MenubarMenu from './ui/menubar/MenubarMenu.vue'
import MenubarTrigger from './ui/menubar/MenubarTrigger.vue'
import MenubarContent from './ui/menubar/MenubarContent.vue'
import MenubarItem from './ui/menubar/MenubarItem.vue'

// Pass { disableTransition: false } to enable transitions
const mode = useColorMode()
</script>

<template>
  <MenubarMenu>
    <MenubarTrigger as-child>
      <Button variant="outline">
        <Icon icon="radix-icons:moon" class="h-[1.2rem] w-[1.2rem] rotate-0 scale-100 transition-all dark:-rotate-90 dark:scale-0" />
        <Icon icon="radix-icons:sun" class="absolute h-[1.2rem] w-[1.2rem] rotate-90 scale-0 transition-all dark:rotate-0 dark:scale-100" />
        <span class="sr-only">Toggle theme</span>
      </Button>
    </MenubarTrigger>
    <MenubarContent align="end">
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
</template>