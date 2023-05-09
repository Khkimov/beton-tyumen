<template>
  <footer class="flex flex-col space-y-4 bg-gray-200 px-5 py-10 md:px-20">
    <div
      class="flex flex-col space-y-4 text-center md:flex-row md:items-start md:justify-between md:space-y-0 md:text-start"
    >
      <TheLogo class="mx-auto md:mx-0" />
      <div class="mx-auto w-48 md:mx-0">Производство и продажа бетона всех марок в Тюмени</div>
      <div>
        <div>Время работы:</div>
        <div class="font-semibold text-black">
          ежедневно<br />
          круглосуточно
        </div>
      </div>
    </div>
    <div
      class="flex flex-col space-y-4 text-center md:flex-row md:items-start md:justify-around md:space-y-0 md:text-start"
    >
      <div>
        <div>Для заказа и консультаций:</div>
        <div class="font-semibold text-black">8(3452)-38-10-03</div>
      </div>
      <div>
        <BaseModal v-if="isCalculateModalOpen" @close="isCalculateModalOpen = false" />
        <div class="animate-pulse text-center md:mr-5">
          <button
            @click="isCalculateModalOpen = true"
            class="h-10 w-40 items-center rounded-full bg-amber-400 text-center"
          >
            Заказать звонок
          </button>
        </div>
      </div>
    </div>
  </footer>
</template>

<script setup>
import { ref } from 'vue'
import TheLogo from '@/components/TheLogo.vue'
import BaseModal from '@/components/BaseModal.vue'

const isCalculateModalOpen = ref(false)
</script>
