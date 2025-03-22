<script setup lang="ts">
import home from "./views/home.vue"
import { useColorMode } from '@vueuse/core'
const mode = useColorMode();
mode.value = 'dark';
</script>

<template>  
  <home/>
</template>
 