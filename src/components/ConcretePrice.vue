<template>
  <div class="rounded border border-gray-200 bg-white p-2 drop-shadow-xl md:w-[600px] md:px-5">
    <h2 class="mb-2 text-2xl font-bold text-black">{{ props.title }}</h2>
    <div
      class="flex flex-col items-center pt-3 text-xl font-semibold text-black lg:flex-row"
      v-for="(item, index) in props.modelValue"
      :style="index % 2 === 0 ? 'background: rgb(229 231 235);' : 'background: white;'"
      :key="item.label"
    >
      <div class="flex">
        <div class="mr-1 w-36">
          {{ item.label }}
          <span v-if="item.mark" class="text-sm text-gray-600">({{ item.mark }})</span>
        </div>
        <div class="w-36">от {{ item.price }} р./м3</div>
      </div>
      <div class="text-sm text-gray-600 lg:ml-4">{{ item.forWhat }}</div>
    </div>
  </div>
</template>

<script setup>
const props = defineProps({
  modelValue: Array,
  title: String
})
</script>
