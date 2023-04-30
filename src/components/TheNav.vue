<script setup>
import {ref} from "vue";
import { TruckIcon, CalculatorIcon, PrinterIcon } from '@heroicons/vue/24/outline'

const navItems = ref({
'доставка': TruckIcon,
'рассчитать': CalculatorIcon,
'pdf файл': PrinterIcon
})
</script>
<template>
  <nav class="sticky bottom-0 z-10 bg-white text-3x1">
    <ul class="flex items-center justify-around border-t">
      <li v-for="(icon, tag) in navItems" :key="tag" class="flex-1">
        <a :href="`#${tag}`" class="flex flex-col items-center p-2 text-xs capitalize">
          <component :is="icon" class="h-6 w-6" /> {{ tag }}
        </a>
      </li>
    </ul>
  </nav>
</template>