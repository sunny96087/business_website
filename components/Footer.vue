<!-- components/Footer.vue -->
<script setup lang="ts"></script>

<template>
  <div class="bg">
    <footer
      class="max-w-[1200px] md:m-auto flex flex-col gap-10 px-8 py-10 md:flex-row md:items-center md:justify-between"
    >
      <div class="flex flex-col items-center md:items-start">
        <nuxtLink to="/" class="paytone-one-regular text-[26px] md:text-[32px] mb-6">2Fish</nuxtLink>
        <p class="text-[#3B3B3B]">若有數位產品設計和開發相關問題</p>
        <p class="text-[#3B3B3B]">歡迎填寫表單，或直接與我聯絡！</p>
        <p class="mt-6 text-[#919191]">歡迎填寫表單，或直接與我聯絡！</p>
      </div>

      <div class="flex flex-col items-center gap-6 md:w-[306px]">
        <a
          class="h-[72px] w-full max-w-[306px] rounded-lg bg-black px-6 py-3 text-left text-white hover-opacity-80 cursor-pointer"
        >
          <Icon name="material-symbols:list-alt-outline-rounded" size="46"></Icon>
          填寫表單
        </a>

        <a
          class="w-full max-w-[306px] rounded-lg border border-[#C1C1C1] px-6 py-3 text-left text-[#3B3B3B] bg-white hover-opacity-80 cursor-pointer"
        >
          <Icon name="mdi:instagram" size="46"></Icon>
          2_fish
        </a>

        <a
          class="w-full max-w-[306px] rounded-lg border border-[#C1C1C1] px-6 py-3 text-left text-[#3B3B3B] bg-white hover-opacity-80 cursor-pointer"
        >
          <Icon name="mdi:facebook-box" size="46"></Icon>
          2_fish
        </a>
      </div>
    </footer>
  </div>
</template>

<style scoped>
.bg {
  background: url('~/assets/images/footer/footer-sm.png') no-repeat center center;
  background-size: cover;
}

@media screen and (min-width: 512px) {
  .bg {
    background: url('~/assets/images/footer/footer-lg.png') no-repeat center center;
    background-size: cover;
  }
}
</style>
