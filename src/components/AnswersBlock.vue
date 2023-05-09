<template>
  <div class="px-5">
    <h2 class="mt-5 text-center text-xl font-semibold text-black md:text-2xl md:font-bold">
      Ответы на самые частые вопросы клиентов нашему менеджеру
    </h2>
    <div
      v-for="(item, index) in answers"
      :key="index"
      class="mx-auto my-5 max-w-sm border-b bg-white pb-5"
    >
      <div class="flex items-center justify-between">
        <div class="text-xl">{{ item.question }}</div>
        <div v-if="!isOpen" @click="selectItem(index)">
          <button class="h-10 w-10 p-1 text-gray-500 focus:outline-none">
            <PlusIcon v-if="!isOpen" />
            <XMarkIcon v-if="isOpen && index === selectedItem" />
          </button>
        </div>
        <div v-else-if="isOpen && index === selectedItem">
          <button @click="isOpen = false" class="h-10 w-10 p-1 text-gray-500 focus:outline-none">
            <XMarkIcon />
          </button>
        </div>
        <div v-else>
          <button class="h-10 w-10 p-1 text-gray-500 focus:outline-none">
            <PlusIcon />
          </button>
        </div>
      </div>
      <div v-if="isOpen && index === selectedItem">
        {{ item.answer }}
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue'
import { PlusIcon } from '@heroicons/vue/24/outline'
import { XMarkIcon } from '@heroicons/vue/24/outline'
const isOpen = ref(false)
const selectedItem = ref(0)
const isActive = ref(false)

const answers = [
  {
    id: 0,
    question: 'За сколько по времени делать заказ?',
    answer:
      'Заказать бетон на нужное время, можно по звонку в день планируемой заливки или заблаговременно, за один день, до неё.'
  },
  {
    id: 1,
    question: 'Сомневаетесь в своем конечном объеме? Что делать?',
    answer:
      'Закажите последний миксер, по факту. Диспетчер, перед отправкой последней машины уточнит, сколько кубометров в неё грузить. Не забудьте заново пересчитать объем в опалубке.'
  },
  {
    id: 2,
    question: 'Сложно подъехать к заливаемому объекту?',
    answer:
      'Вы сможете отравить фотографию объекта нам на WhatsApp. Специалист найдет решение: подберет автобетононасос, миксер с длинным лотком или миксер-вездеход.'
  },
  {
    id: 3,
    question: 'Каким должен быть интервал между миксерами?',
    answer:
      'Рекомендуемый интервал между машинами, 40 минут. За это время Ваша бригада успеет качественно, без спешки принять бетон. При работе с автобетононасосом рекомендуемое время, 10-20 минут.'
  }
]

const selectItem = (i) => {
  isOpen.value = true
  selectedItem.value = i
  answers.forEach((item, index) => {
    return (isActive.value = item === answers[index])
  })
}
</script>
