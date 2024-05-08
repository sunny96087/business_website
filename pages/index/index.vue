<!-- 首頁 -->
<script setup lang="ts">
import { showToast, openDialog, showLoading, hideLoading } from '~/store/eventBus'
</script>

<template>
  <div class="index">
    <!-- * banner -->
    <section class="flex flex-col gap-6 overflow-hidden lg:flex-row-reverse">
      <div class="pic relative w-full lg:mb-20 lg:min-w-[60%]">
        <img src="~assets/images/home/banner.png" class="pic-auto" alt="" />
        <div class="decorate-1 absolute"></div>
        <div class="decorate-2 absolute"></div>
        <div class="decorate-3 absolute"></div>
        <div class="decorate-4 absolute"></div>
        <div class="decorate-5 absolute"></div>
        <div class="decorate-6 absolute"></div>
      </div>

      <div class="flex flex-col items-center justify-center px-5 lg:pl-6 lg:pr-0 lg:items-start">
        <h2 class="mb-6 text-[32px] text-[#3B3B3B] lg:text-[40px]">Hi！我是 2fish</h2>
        <p class="mb-4 text-[20px] leading-[32px] text-[#5B5B5B]">
          具有 1 年經驗的前端工程師 & UIUX 設計師，技術雙修並行，熱衷於優化使用者的網頁體驗
        </p>
        <p class="mb-6 leading-[24px] text-[#C1C1C1]">
          WEB DEVELOPMENT / BRANDING / UI / UX / APP DESIGN
        </p>

        <!-- 社群 -->
        <div class="flex gap-4">
          <a href="#" class="hover-opacity-80">
            <Icon name="mdi:instagram" size="24" class="text-[#5B5B5B]"></Icon>
          </a>
          <a href="#" class="hover-opacity-80">
            <Icon name="mdi:facebook-box" size="24" class="text-[#5B5B5B]"></Icon>
          </a>
          <a href="#" class="hover-opacity-80">
            <Icon name="mdi:youtube" size="24" class="text-[#5B5B5B]"></Icon>
          </a>
          <a href="#" class="hover-opacity-80">
            <Icon name="mdi:linkedin" size="24" class="text-[#5B5B5B]"></Icon>
          </a>
          <a href="#" class="hover-opacity-80">
            <Icon name="mdi:gmail" size="24" class="text-[#5B5B5B]"></Icon>
          </a>
          <a href="#" class="hover-opacity-80">
            <Icon name="mdi:phone" size="24" class="text-[#5B5B5B]"></Icon>
          </a>
        </div>
      </div>
    </section>

    <title-component title="作品介紹" class="my-10 lg:mb-[80px] lg:mt-[120px]"></title-component>

    <!-- * portfolio - pc -->
    <section class="hidden lg:block">
      <div class="p1-pc relative h-[800px]">
        <div class="pc-card left-[55%] top-1/2 -translate-y-1/2">
          <h3 class="mb-2 text-[28px] text-white">星際旅行訂票平台</h3>
          <p class="mb-6 text-white">悠遊宇宙的夢想，從這裡開始實現</p>

          <div class="mb-10 flex gap-4">
            <div class="card-tag">網頁設計</div>
            <div class="card-tag">響應式設計</div>
            <div class="card-tag">Bootstrap</div>
          </div>
          <hr class="mb-10 border-[#F1F1F1]" />
          <button class="card-btn hover-opacity-80">
            完整介紹 <Icon name="material-symbols:arrow-right-alt-rounded" size="24"></Icon>
          </button>
        </div>
      </div>
      <div class="p2-pc relative h-[800px]">
        <div class="absolute bottom-0 left-0 right-[50%] top-0 bg-black bg-opacity-30"></div>
        <div class="pc-card right-[55%] top-1/2 -translate-y-1/2">
          <h3 class="mb-2 text-[28px] text-white">理財APP</h3>
          <p class="mb-6 text-white">連動帳戶與行動支付，讓 AI 提供您最好的理財建議</p>

          <div class="mb-10 flex gap-4">
            <div class="card-tag">APP設計</div>
            <div class="card-tag">iOS</div>
            <div class="card-tag">React</div>
          </div>
          <hr class="mb-10 border-[#F1F1F1]" />
          <button class="card-btn hover-opacity-80">
            完整介紹 <Icon name="material-symbols:arrow-right-alt-rounded" size="24"></Icon>
          </button>
        </div>
      </div>
      <div class="p3-pc relative h-[800px]">
        <div class="pc-card left-[55%] top-1/2 -translate-y-1/2">
          <h3 class="mb-2 text-[28px] text-white">醫美診所官網</h3>
          <p class="mb-6 text-white">永保青春的秘密，從粹究開始</p>

          <div class="mb-10 flex gap-4">
            <div class="card-tag">網頁設計</div>
            <div class="card-tag">響應式設計</div>
            <div class="card-tag">ＷordPress</div>
          </div>
          <hr class="mb-10 border-[#F1F1F1]" />
          <button class="card-btn hover-opacity-80">
            完整介紹 <Icon name="material-symbols:arrow-right-alt-rounded" size="24"></Icon>
          </button>
        </div>
      </div>
    </section>
    <!-- * portfolio - mb -->
    <section class="mb-20 block lg:hidden">
      <div class="p1">
        <div class="pic sm:h-[500px]">
          <img src="~assets/images/home/p1.png" alt="" class="pic-auto" />
        </div>

        <div class="mt-6 flex flex-col items-center">
          <h3 class="mb-2 text-[20px] text-[#1E1E1E]">星際旅行訂票平台</h3>
          <p class="mb-4 text-[#5B5B5B]">悠遊宇宙的夢想，從這裡開始實現</p>
          <div class="mb-5 flex gap-4">
            <div class="mb-card-tag">網頁設計</div>
            <div class="mb-card-tag">響應式設計</div>
            <div class="mb-card-tag">Bootstrap</div>
          </div>
          <button class="mb-card-btn hover-opacity-80">
            完整介紹 <Icon name="material-symbols:arrow-right-alt-rounded" size="24"></Icon>
          </button>
        </div>
      </div>
      <div class="p2 mt-[48px]">
        <div class="pic sm:h-[500px]">
          <img src="~assets/images/home/p2.png" alt="" class="pic-auto" />
        </div>

        <div class="mt-6 flex flex-col items-center">
          <h3 class="mb-2 text-[20px] text-[#1E1E1E]">星際旅行訂票平台</h3>
          <p class="mb-4 text-[#5B5B5B]">悠遊宇宙的夢想，從這裡開始實現</p>
          <div class="mb-5 flex gap-4">
            <div class="mb-card-tag">網頁設計</div>
            <div class="mb-card-tag">響應式設計</div>
            <div class="mb-card-tag">Bootstrap</div>
          </div>
          <button class="mb-card-btn hover-opacity-80">
            完整介紹 <Icon name="material-symbols:arrow-right-alt-rounded" size="24"></Icon>
          </button>
        </div>
      </div>
      <div class="p3 mt-[48px]">
        <div class="pic sm:h-[500px]">
          <img src="~assets/images/home/p3.png" alt="" class="pic-auto" />
        </div>

        <div class="mt-6 flex flex-col items-center">
          <h3 class="mb-2 text-[20px] text-[#1E1E1E]">星際旅行訂票平台</h3>
          <p class="mb-4 text-[#5B5B5B]">悠遊宇宙的夢想，從這裡開始實現</p>
          <div class="mb-5 flex gap-4">
            <div class="mb-card-tag">網頁設計</div>
            <div class="mb-card-tag">響應式設計</div>
            <div class="mb-card-tag">Bootstrap</div>
          </div>
          <button class="mb-card-btn hover-opacity-80">
            完整介紹 <Icon name="material-symbols:arrow-right-alt-rounded" size="24"></Icon>
          </button>
        </div>
      </div>
    </section>
    <!-- * services -->
    <section class="sec-service bg-[#FAFAFA]">
      <title-component
        title="服務項目"
        class="pb-10 pt-20 lg:pb-[80px] lg:pt-[120px]"
      ></title-component>

      <div class="flex flex-col gap-6 lg:flex-row lg:justify-center">
        <div class="service-item">
          <Icon name="material-symbols-light:design-services-outline-rounded" size="80"></Icon>
          <div class="text-nowrap">平面設計</div>
        </div>
        <div class="service-item">
          <Icon name="iconoir:design-nib-solid" size="80"></Icon>
          <div class="text-nowrap">UI 設計</div>
        </div>
        <div class="service-item">
          <Icon name="heroicons:computer-desktop" size="80"></Icon>
          <div class="text-nowrap">切版服務</div>
        </div>
        <div class="service-item">
          <Icon name="ph:code" size="80"></Icon>
          <div class="text-nowrap">前端開發</div>
        </div>
      </div>

      <div class="mt-10 text-center text-[20px] text-[#3B3B3B] lg:mt-20 lg:text-[28px]">
        想要合作或瞭解更多？
      </div>
      <div class="mt-6 pb-20 text-center lg:mt-10 lg:pb-[120px]">
        <button class="card-btn hover-opacity-80">
          詳細內容與合作流程 <Icon name="material-symbols:arrow-right-alt-rounded" size="24"></Icon>
        </button>
      </div>
    </section>

    <!-- * blog -->
    <section class="py-20 lg:py-[120px]">
      <title-component title="精選文章" class="mb-10 lg:mb-20"></title-component>
      <!-- swiper 後補 -->
    </section>
  </div>
</template>

<style scoped>
/* banner 裝飾 */
.decorate-1 {
  @apply -left-[23px] top-[28px] h-[25px] w-[86px] lg:-left-[81px] lg:top-[40px] lg:h-[68px] lg:w-[241px];
  background: rgba(178, 178, 178, 0.2);
}

.decorate-2 {
  @apply -left-[30px] top-[63px] h-[15px] w-[49px] lg:-left-[96px] lg:top-[120px] lg:h-[40px] lg:w-[139px];
  background: rgba(178, 178, 178, 0.2);
}

.decorate-3 {
  @apply -bottom-[10px] left-[8%] h-[37px] w-[37px] rounded-full border border-dashed lg:-bottom-[20px] lg:left-[22%] lg:h-[105px] lg:w-[105px] lg:border-[5px];
  border-color: rgba(217, 217, 217, 0.4);
}

.decorate-4 {
  @apply -bottom-[17px] left-[12%] h-[50px] w-[50px] rounded-full lg:-bottom-[70px] lg:left-[26%] lg:h-[142px] lg:w-[142px];
  background: rgba(130, 130, 130, 0.2);
}

.decorate-5 {
  @apply -bottom-[17px] right-[6%] h-[47px] w-[47px] rounded-full lg:-bottom-[36px] lg:right-[1%] lg:h-[131px] lg:w-[131px];
  background: rgba(130, 130, 130, 0.2);
}

.decorate-6 {
  @apply -bottom-[35px] -right-[5%] h-[96px] w-[96px] rounded-full border border-dashed lg:-bottom-[85px] lg:-right-[28%] lg:h-[266px] lg:w-[266px] lg:border-[5px];
  border-color: rgba(217, 217, 217, 0.4);
}

.p1-pc {
  background: url('~/assets/images/home/p1-pc.png') no-repeat center center;
  background-size: cover;
  background-attachment: fixed;
}

.p2-pc {
  background: url('~/assets/images/home/p2-pc.png') no-repeat center center;
  background-size: cover;
  background-attachment: fixed;
}

.p3-pc {
  background: url('~/assets/images/home/p3-pc.png') no-repeat center center;
  background-size: cover;
  background-attachment: fixed;
}

.pc-card {
  @apply absolute inline-flex flex-col rounded-[24px] px-10 pb-[56px] pt-20;
  background: rgba(255, 255, 255, 0.1);
  backdrop-filter: blur(8px);
}

.card-tag {
  @apply rounded-[16px] bg-white px-3 py-1 text-[#3B3B3B];
}

.card-btn {
  @apply inline items-center self-center rounded-[5px] bg-black px-8 py-4 text-white;
}

.mb-card-tag {
  @apply rounded-[16px] bg-[#F1F1F1] px-3 py-1 text-[#3B3B3B];
}

.mb-card-btn {
  @apply inline items-center self-center rounded-[5px] bg-black px-4 py-2 text-white;
}

.service-item {
  @apply flex h-[246px] w-[266px] flex-col items-center justify-center gap-6 self-center rounded-[16px] text-[24px] text-white;
  background: linear-gradient(315deg, #1e1e1e 0%, #1e1e1e 49%, #000000 50%);
}

@media screen and (min-width: 1024px) {
  .sec-service {
    background: url('~/assets/images/home/sec3-bg-pc.png') no-repeat center center;
    background-size: cover;
  }
}
</style>
