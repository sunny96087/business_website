<!-- connection -->
<script setup lang="ts">
import { showToast, openDialog, showLoading, hideLoading } from '~/store/eventBus'
const name = ref('')
const email = ref('')
const content = ref('')
function submit() {
  let data = {
    name: name.value,
    email: email.value,
    content: content.value
  }
  console.log(data)

  showToast('成功送出表單，我們將於 7 日內回覆您！')

  // 清空表單
  name.value = ''
  email.value = ''
  content.value = ''
}
</script>

<template>
  <div class="connection px-4 pb-[40px] lg:pb-[80px]">
    <section class="pb-[40px] lg:pb-[80px]">
      <title-component title="聯絡我們" class="pt-20 lg:pt-[120px]"></title-component>
      <p class="mt-4 text-center text-[#919191] lg:mt-6">或留下您寶貴的想法</p>
    </section>
    <div class="mx-auto flex max-w-[800px] flex-col gap-4 rounded-2xl border p-8 shadow">
      <input v-model="name" type="text" placeholder="請輸入您的姓名" class="input" />
      <input v-model="email" type="text" placeholder="請輸入您的信箱" class="input" />
      <textarea v-model="content" class="area input" placeholder="請輸入您的想法"></textarea>
      <button
        :disabled="!name || !email || !content"
        @click="submit"
        class="button mt-4 w-full rounded-lg border-none bg-sky-700 px-3 py-2 text-white"
      >
        送出
      </button>
    </div>
  </div>
</template>
<style scoped>
.input {
  @apply border p-2 rounded-md;
}

.button:disabled {
  @apply bg-gray-500 opacity-50 cursor-not-allowed;
  /* 這裡可以添加更多的樣式，例如改變背景顏色或邊框樣式 */
}
</style>
