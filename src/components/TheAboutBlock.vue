<template>
  <div class="flex w-full flex-col md:flex-row">
    <div class="px-5 py-10 md:relative md:w-2/3 lg:w-3/4">
      <h1 class="text-center text-2xl font-black md:text-3xl">
        При заказе от 0.5м³ доставка по городу Тюмень бесплатно
      </h1>
      <BaseModal v-if="isCalculateModalOpen" @close="isCalculateModalOpen = false" />
      <div class="flex flex-col justify-center md:mt-10 md:flex-row md:space-x-4">
        <div class="mt-5 h-20 animate-pulse text-center">
          <button
            @click="isCalculateModalOpen = true"
            class="h-10 w-40 items-center rounded-full bg-amber-400 text-center"
          >
            Рассчитать
          </button>
        </div>
        <div class="w-300 flex flex-col text-center font-medium md:text-start">
          <p class="mb-2">На прямую от производителя (без посредников)</p>
          <p class="mb-2">Быстрая доставка собственными автобетоносмесителями от 0,5м3</p>
          <p class="mb-2">Имеются бетононасосы от 11 до 37 метров</p>
        </div>
      </div>
      <div
        class="grid grid-cols-1 md:absolute md:inset-x-0 md:bottom-0 md:grid-cols-2 lg:grid-cols-3"
      >
        <div class="mx-auto flex items-center md:mx-0">
          <div class="h-15 w-15 flex items-center">
            <img class="w-full" src="../assets/truck-images/1__1.png" />
          </div>
          <div class="w-72">Подберём правильную марку</div>
        </div>
        <div class="mx-auto flex items-center md:mx-0">
          <div class="h-15 w-15 flex items-center">
            <img class="w-full" src="../assets/truck-images/2__1.png" />
          </div>
          <div class="w-72">Рассчитаем точный объём бетона</div>
        </div>
        <div class="mx-auto flex items-center md:col-span-2 lg:col-span-1 lg:mx-0">
          <div class="h-15 w-15 flex items-center">
            <img class="w-full" src="../assets/truck-images/3__1.png" />
          </div>
          <div class="w-72">Расскажем, как получить фундамент без трещин на всю жизнь!</div>
        </div>
      </div>
    </div>
    <div class="px-10 pt-10 md:w-1/3 md:px-10 lg:w-1/4">
      <div class="mb-4 text-center text-xl font-bold text-sky-700">
        Доставка маленькими (мини миксер) и большими миксерами от 0.5м3 (куба)
      </div>
      <div>
        <div class="text-center font-medium">Большой миксер</div>
        <img class="w-full" src="../assets/truck-images/big-truck.png" />
      </div>
      <div>
        <div class="text-center font-medium">Маленький миксер</div>
        <img class="w-full" src="../assets/truck-images/blue-truck-mini.png" />
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue'
import BaseModal from '@/components/BaseModal.vue'
const isCalculateModalOpen = ref(false)
</script>
