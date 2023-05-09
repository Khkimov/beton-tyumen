<script setup>
import { ref } from 'vue'
import BaseModal from '@/components/BaseModal.vue'
import { TruckIcon, CalculatorIcon } from '@heroicons/vue/24/outline'

const isCalculateModalOpen = ref(false)
</script>
<template>
  <BaseModal v-if="isCalculateModalOpen" @close="isCalculateModalOpen = false" />
  <div class="sticky bottom-0 z-10 bg-white md:hidden">
    <div class="flex items-center justify-around border-t">
      <div class="flex-1">
        <div class="flex flex-col items-center p-2 text-xs" @click="isCalculateModalOpen = true">
          <div class="h-6 w-6">
            <CalculatorIcon />
          </div>
          <div>Рассчитать</div>
        </div>
      </div>
      <div class="flex-1">
        <div class="flex flex-col items-center p-2 text-xs">
          <div class="h-6 w-6">
            <TruckIcon />
          </div>
          <div>Доставка</div>
        </div>
      </div>
    </div>
  </div>
</template>
