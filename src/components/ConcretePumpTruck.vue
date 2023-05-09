<template>
  <div
    class="mb-4 rounded border border-gray-200 bg-white p-2 drop-shadow-xl md:mb-0 md:w-[778px] md:px-5"
  >
    <h2 class="mb-2 text-2xl font-bold text-black">Автобетононасосы</h2>
    <div class="flex flex-col md:flex-row">
      <div class="text-center md:flex md:w-96 md:flex-wrap">
        <div
          v-for="(item, index) in concretePumpTruck"
          :key="item.pumpArrow"
          class="bg-gray-200 p-2 md:w-44"
          :style="index % 3 === 0 ? 'background: rgb(229 231 235);' : 'background: white;'"
        >
          <div class="text-sm text-gray-600">Стрела {{ item.pumpArrow }} метр</div>
          <div class="text-xl font-semibold text-black">от {{ item.price }} р./час</div>
        </div>
      </div>
      <div class="py-2 md:w-72">
        <img class="w-full" src="../assets/truck-images/concrete-pump-truck.png" />
      </div>
    </div>
  </div>
</template>

<script setup>
const concretePumpTruck = [
  {
    pumpArrow: 11,
    price: 1000
  },
  {
    pumpArrow: 11,
    price: 1000
  },
  {
    pumpArrow: 11,
    price: 1000
  },
  {
    pumpArrow: 11,
    price: 1000
  }
]
</script>
