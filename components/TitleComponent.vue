<script setup lang="ts">
import { defineProps } from 'vue'

// 定義 props
const props = defineProps({
  title: {
    type: String,
    required: true
  }
})
</script>

<template>
  <div class="flex gap-4 justify-center">
    <div class="flex items-center">
        <div class="w-[6px] h-[6px] bg-[#C1C1C1] rounded-full"></div>
        <div class="w-[50px] lg:w-[94px] h-[1px] bg-[#C1C1C1]"></div>
    </div>

    <h1 class="text-[24px] lg:text-[32px] text-[#3B3B3B]">{{ title }}</h1>

    <div class="flex items-center">
        <div class="w-[50px] lg:w-[94px] h-[1px] bg-[#C1C1C1]"></div>
        <div class="w-[6px] h-[6px] bg-[#C1C1C1] rounded-full"></div>
    </div>
  </div>
</template>

<style scoped></style>
