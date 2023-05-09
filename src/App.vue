<template>
  <TheHeader />
  <main class="flex flex-grow flex-col">
    <TheAboutBlock />
    <ThePricesBlock />
    <CalculateBlock />
    <ServiceBlock />
    <AnswersBlock />
  </main>
  <TheNav />
</template>
<script setup>
import TheHeader from '@/components/TheHeader.vue'
import TheNav from '@/components/TheNav.vue'
import TheAboutBlock from '@/components/TheAboutBlock.vue'
import ThePricesBlock from '@/components/ThePricesBlock.vue'
import CalculateBlock from '@/components/CalculateBlock.vue'
import ServiceBlock from '@/components/ServiceBlock.vue'
import AnswersBlock from '@/components/AnswersBlock.vue'
</script>
