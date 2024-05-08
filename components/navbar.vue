<script setup lang="ts">

import { APIStore } from '~/store/apiService'
const store = APIStore()
import { showToast, openDialog, showLoading, hideLoading } from '~/store/eventBus'
const router = useRouter()


const menu = ref(false)


</script>

<template>
  <div class="sticky top-0 z-20 border-b border-gray-200 bg-white py-3">
    <div class="relative m-auto flex max-w-[1200px] items-center justify-between px-6">
      <nuxtLink to="/" class="paytone-one-regular text-[26px]">2Fish</nuxtLink>

      <div class="flex gap-10 justify-center items-center">
        <nuxtLink to="/" class="leading-[28px]">首頁</nuxtLink>
        <nuxtLink to="/" class="leading-[28px]">作品集</nuxtLink>
        <nuxtLink to="/" class="leading-[28px]">服務項目</nuxtLink>
        <nuxtLink to="/" class="leading-[28px]">部落格</nuxtLink>
        <nuxtLink to="/" class="leading-[28px]">聯絡我</nuxtLink>



      </div>
    </div>
  </div>
</template>

<style scoped>

</style>
