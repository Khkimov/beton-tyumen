<template>
  <div class="p-5 md:px-0">
    <BaseModal v-if="isCalculateModalOpen" @close="isCalculateModalOpen = false" />
    <div class="flex flex-col md:flex-row md:items-center md:justify-center">
      <div class="animate-pulse text-center md:mr-5">
        <button
          @click="isCalculateModalOpen = true"
          class="h-10 w-40 items-center rounded-full bg-amber-400 text-center"
        >
          Рассчитать
        </button>
      </div>
      <div class="md:w-300 flex flex-col text-center font-medium md:text-start">
        <p class="mb-2">На прямую от производителя (без посредников)</p>
        <p class="mb-2">Быстрая доставка собственными автобетоносмесителями от 0,5м3</p>
        <p class="mb-2">Имеются бетононасосы от 11 до 37 метров</p>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue'
import BaseModal from '@/components/BaseModal.vue'

const isCalculateModalOpen = ref(false)
</script>
