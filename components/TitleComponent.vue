<script setup lang="ts">
import { defineProps } from 'vue'

// 定義 props
const props = defineProps({
  title: {
    type: String,
    required: true
  },
  color: {
    type: String
  }
})
</script>

<template>
  <div v-if="color === 'white'" class="flex justify-center gap-4">
    <div class="flex items-center">
      <div class="h-[6px] w-[6px] rounded-full bg-white"></div>
      <div class="h-[1px] w-[50px] bg-white lg:w-[94px]"></div>
    </div>

    <h1 class="text-[24px] text-white lg:text-[32px]">{{ title }}</h1>

    <div class="flex items-center">
      <div class="h-[1px] w-[50px] bg-white lg:w-[94px]"></div>
      <div class="h-[6px] w-[6px] rounded-full bg-white"></div>
    </div>
  </div>
  <div v-else class="flex justify-center gap-4">
    <div class="flex items-center">
      <div class="h-[6px] w-[6px] rounded-full bg-[#C1C1C1]"></div>
      <div class="h-[1px] w-[50px] bg-[#C1C1C1] lg:w-[94px]"></div>
    </div>

    <h1 class="text-[24px] text-[#3B3B3B] lg:text-[32px]">{{ title }}</h1>

    <div class="flex items-center">
      <div class="h-[1px] w-[50px] bg-[#C1C1C1] lg:w-[94px]"></div>
      <div class="h-[6px] w-[6px] rounded-full bg-[#C1C1C1]"></div>
    </div>
  </div>
</template>

<style scoped></style>
