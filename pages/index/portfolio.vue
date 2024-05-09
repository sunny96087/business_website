<!-- portfolio -->
<script setup lang="ts">
import { showToast, openDialog, showLoading, hideLoading } from '~/store/eventBus'
</script>

<template>
  <section class="w-full bg-[#FAFAFA] px-8 pb-20 pt-10 md:pt-20">
    <div class="flex flex-col items-center md:h-[168px] md:flex-row md:justify-center">
      <Icon name="bxs:quote-alt-left" size="56" class="text-[#E9E9E9] md:self-start"></Icon>
      <div class="text-center text-[20px] text-[#1E1E1E] md:text-[24px]">
        <p class="mb-2">讓使用者在觀賞與使用的旅程中，發現設計的價值</p>
        <p>而我在設計與開發的過程中，看見自己的價值</p>
      </div>
      <div class="hidden md:block md:self-end">
        <Icon name="bxs:quote-alt-right" size="56" class="text-[#E9E9E9]"></Icon>
      </div>
    </div>

    <div class="mt-10 flex flex-col items-center gap-5 px-8 md:flex-row md:justify-center md:gap-10 md:max-w-[640px] md:mx-auto">
      <div class=" flex flex-col items-center">
        <p class="text-[#5B5B5B]">2B經驗</p>
        <div class="mt-[2px] h-[2px] w-6 bg-[#C1C1C1]"></div>
        <p class="mt-2 text-center text-[#3B3B3B]">
          內部監控系統、庫存系統、採購系統、行銷整合系統
        </p>
      </div>

      <div class=" flex flex-col items-center">
        <p class=" text-[#5B5B5B]">2C經驗</p>
        <div class="mt-[2px] h-[2px] w-6 bg-[#C1C1C1]"></div>
        <p class="mt-2 text-center text-[#3B3B3B]">
          跨國美妝保養電商、個人品牌網站、醫美網站、電子商務
        </p>
      </div>
    </div>
  </section>

  
  <!-- 作品換頁 - mb -->
  <section class="bg-white py-[80px] lg:hidden"></section>

  <!-- 作品輪播圖 - pc -->
  <section class="bg-white py-[120px] hidden lg:block"></section>
</template>
<style scoped></style>
