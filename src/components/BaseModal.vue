<template>
  <div
    class="fixed inset-0 z-10 focus:outline-none"
    ref="modalRef"
    tabindex="-1"
    @keydown.esc="emit('close')"
  >
    <transition
      appear
      enter-active-class="ease-out duration-200"
      enter-from-class="opacity-0"
      enter-to-class="opacity-100"
      leave-active-class="ease-in duration-75"
      leave-from-class="opacity-100"
      leave-to-class="opacity-0"
    >
      <BaseModalOverlay v-if="isOpen" @click="close" />
    </transition>
    <div v-if="isOpen" class="relative mx-auto my-8 mt-20 max-w-sm bg-white">
      <div class="p-2 text-right">
        <BaseModalButtonClose @click="close" />
      </div>
      <div class="px-6 pb-6">
        <BaseModalContent />
      </div>
    </div>
  </div>
</template>
<script setup>
import BaseModalButtonClose from '@/components/BaseModalButtonClose.vue'
import { onMounted, ref } from 'vue'
import BaseModalOverlay from '@/components/BaseModalOverlay.vue'
import BaseModalContent from '@/components/BaseModalContent.vue'

const emit = defineEmits(['close'])
const modalRef = ref(null)
const isOpen = ref(true)

const close = () => {
  isOpen.value = false
  setTimeout(() => emit('close'), 100)
}
onMounted(() => {
  modalRef.value.focus()
})
</script>
