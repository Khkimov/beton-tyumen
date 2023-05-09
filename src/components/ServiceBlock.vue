<template>
  <div class="bg-gray-200 py-5 text-center">
    <h2 class="mb-10 text-2xl font-bold text-black">Предоставляем уникальный сервис</h2>
    <div class="mx-auto grid w-72 grid-cols-1 content-center gap-4 md:w-[778px] md:grid-cols-2">
      <div
        v-for="item in service"
        :key="item.title"
        class="flex flex-col rounded-lg bg-white shadow-[0_2px_15px_-3px_rgba(0,0,0,0.07),0_10px_20px_-2px_rgba(0,0,0,0.04)] dark:bg-neutral-700 md:max-w-xl"
      >
        <div class="flex flex-col justify-start p-6">
          <h5 class="mb-2 text-xl font-medium text-neutral-800 dark:text-neutral-50">
            {{ item.title }}
          </h5>
          <div class="mb-4 text-base text-neutral-600 dark:text-neutral-200">
            {{ item.text }}
          </div>
        </div>
        <img class="mt-auto w-full object-cover" :src="item.image" alt="" />
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue'
import documents from '../assets/card-images/1.png'
import terminalPayments from '../assets/card-images/2.png'
import truck from '../assets/card-images/3.png'
import truckW from '../assets/card-images/4.png'

const service = ref([
  {
    title: 'ДОКУМЕНТЫ НА РУКИ',
    text: 'Договор, паспорт качества, товарная накладная, протокол испытания вашего образца бетона от нашей лаборатории',
    image: documents
  },
  {
    title: 'НИКАКОЙ ПРЕДОПЛАТЫ',
    text: 'Оплатите на месте приёмки, через терминал или по выставленному от нас счёту',
    image: terminalPayments
  },
  {
    title: 'БЫСТРАЯ ДОСТАВКА',
    text: 'По звонку, через 45 минут, бетон у вас. Без пробок и простоев ваших работников',
    image: truck
  },
  {
    title: 'РАЗГРУЗКА БЕЗ ДОПЛАТ',
    text: 'До 1 часа на разгрузку, даём бесплатно',
    image: truckW
  }
])
</script>
