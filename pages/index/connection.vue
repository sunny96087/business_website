<!-- connection -->
<script setup lang="ts">
import { showToast, openDialog, showLoading, hideLoading } from '~/store/eventBus'
</script>

<template>
  <div class="connection px-4 pb-[40px] lg:pb-[80px]">
    <section class="pb-[40px] lg:pb-[80px]">
      <title-component title="聯絡我們" class="pt-20 lg:pt-[120px]"></title-component>
      <p class="mt-4 text-center text-[#919191] lg:mt-6">或留下您寶貴的想法</p>
    </section>
    <div class="mx-auto flex max-w-[1200px] flex-col gap-4 rounded-2xl border p-8 shadow">
      <input type="text" placeholder="請輸入您的姓名" class="input" />
      <input type="text" placeholder="請輸入您的信箱" class="input" />
      <textarea class="area input" placeholder="請輸入您的想法"></textarea>
      <button class="button mt-4 w-full rounded-lg border-none bg-sky-700 px-3 py-2 text-white">
        送出
      </button>
    </div>
  </div>
</template>
<style scoped>
.input{
  @apply border ;
}
</style>
