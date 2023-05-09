<template>
  <div class="text-black-900 mb-2 text-center text-xl font-bold">
    Оставьте заявку на расчёт стоимости доставки бетона
  </div>
  <div class="text-center text-sm">
    Введите Ваш номер телефона и адрес доставки. Менеджер свяжется с Вами в течение 5 минут,
    проконсультирует и скажет точную стоимость доставки бетона нужной марки до вашего объекта.
  </div>
  <div>
    <form class="mb-4 px-8 pb-8 pt-6" ref="form" @submit.prevent="sendEmail">
      <div class="mb-4">
        <input
          class="focus:shadow-outline w-full appearance-none rounded border px-3 py-2 leading-tight text-gray-700 shadow focus:outline-none"
          type="tel"
          name="phone"
          :value="inputFieldReset"
          placeholder="Введите телефон"
        />
      </div>
      <div class="mb-4">
        <input
          class="focus:shadow-outline w-full appearance-none rounded border px-3 py-2 leading-tight text-gray-700 shadow focus:outline-none"
          type="number"
          name="volume"
          :value="inputFieldReset"
          placeholder="Требуемый объем (м³)"
        />
      </div>
      <div class="mb-4">
        <input
          class="focus:shadow-outline w-full appearance-none rounded border px-3 py-2 leading-tight text-gray-700 shadow focus:outline-none"
          type="text"
          name="brand"
          :value="inputFieldReset"
          placeholder="Требуемая марка"
        />
      </div>
      <div class="mb-4">
        <input
          class="focus:shadow-outline w-full appearance-none rounded border px-3 py-2 leading-tight text-gray-700 shadow focus:outline-none"
          type="text"
          name="address"
          :value="inputFieldReset"
          placeholder="Адрес доставки"
        />
      </div>
      <div class="mb-4">
        <input
          class="focus:shadow-outline w-full appearance-none rounded border px-3 py-2 leading-tight text-gray-700 shadow focus:outline-none"
          type="text"
          name="date"
          :value="inputFieldReset"
          placeholder="Примерная дата заливки"
        />
      </div>
      <div class="text-center md:mr-5">
        <button
          type="submit"
          class="h-10 w-40 cursor-pointer items-center rounded-full bg-amber-400 text-center hover:bg-amber-500"
        >
          Отправить
        </button>
      </div>
      <div v-if="isLoading" class="text-center text-green-500">Ваша заявка отправлено</div>
    </form>
  </div>
</template>
<script setup>
import { ref } from 'vue'
import emailJs from '@emailjs/browser'

const form = ref(null)
const inputFieldReset = ref(null)
const isLoading = ref(false)
const sendEmail = () => {
  emailJs
    .sendForm('service_q39dow7', 'template_74iaq6g', form.value, '36FiV35OaAiyu8NFf')
    .then((response) => {
      if (response.status === 200) {
        isLoading.value = true
      }
      inputFieldReset.value = ' '
    })
}
</script>
