<template>
  <div
    class="grid grid-cols-1 content-center space-y-4 bg-gray-200 px-1 py-5 sm:px-10 md:space-y-12 md:px-0"
  >
    <div class="flex flex-col space-y-2 md:mx-auto md:flex-row md:space-x-4 md:space-y-0">
      <ConcretePrice :model-value="concrete" title="Цены на бетон" />
      <DeliveryConcrete />
    </div>
    <div class="flex flex-col space-y-2 md:mx-auto md:flex-row md:space-x-4 md:space-y-0">
      <ConcretePrice :model-value="buildingMixture" title="Цены на раствор" />
      <DeliveryConcrete class="hidden md:block" />
    </div>
    <div class="flex flex-col space-y-2 md:mx-auto md:flex-row md:space-x-4 md:space-y-0">
      <ConcretePrice :model-value="expandedClayConcrete" title="Керамзитобетон" />
      <DeliveryConcrete class="hidden md:block" />
    </div>
    <div class="md:mx-auto">
      <ConcretePumpTruck />
      <DeliveryConcrete class="md:hidden" />
    </div>
  </div>
</template>

<script setup>
import ConcretePrice from '@/components/ConcretePrice.vue'
import DeliveryConcrete from '@/components/DeliveryConcrete.vue'
import ConcretePumpTruck from '@/components/ConcretePumpTruck.vue'

const concrete = [
  {
    label: 'М100',
    mark: 'B 7,5',
    price: 2770,
    forWhat: 'Подготовительные работы'
  },
  {
    label: 'М150',
    mark: 'B 12,5',
    price: 2990,
    forWhat: 'Фундамент бани, гаража'
  },
  {
    label: 'М200',
    mark: 'B 15',
    price: 3100,
    forWhat: 'Фундаменты до 1,5 этажей'
  },
  {
    label: 'М250',
    mark: 'B 20',
    price: 3370,
    forWhat: 'Фундаменты до 2 этажей'
  },
  {
    label: 'М300',
    mark: 'B 22,5',
    price: 3460,
    forWhat: 'Фундаментные плиты'
  },
  {
    label: 'М350',
    mark: 'B 25',
    price: 3580,
    forWhat: 'Многоэтажные здания'
  },
  {
    label: 'М400',
    mark: 'B 30',
    price: 3890,
    forWhat: 'Гидротехническое стр-во'
  }
]
const buildingMixture = [
  {
    label: 'М75-М150',
    mark: '',
    price: 2300,
    forWhat: 'Стяжка пола, заливка кровли'
  },
  {
    label: 'Кладочный',
    mark: '',
    price: 2300,
    forWhat: 'Кирпичная кладка'
  },
  {
    label: 'Штукатурный',
    mark: '',
    price: 2300,
    forWhat: 'Штукатурка стен'
  },
  {
    label: 'Известковый',
    mark: '',
    price: 2400,
    forWhat: 'Жизнеспособность 6 часов'
  }
]
const expandedClayConcrete = [
  {
    label: 'М75',
    mark: '',
    price: 4000,
    forWhat: 'Теплоизоляция стен'
  },
  {
    label: 'М100',
    mark: '',
    price: 4200,
    forWhat: 'Монтаж стен, заливка пола'
  },
  {
    label: 'М150',
    mark: '',
    price: 4500,
    forWhat: 'Монолитные несущие конструкции'
  }
]
</script>
