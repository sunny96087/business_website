<!-- 首頁 -->
<script setup lang="ts">
import { showToast, openDialog, showLoading, hideLoading } from '~/store/eventBus'

import blogImage1 from '~/assets/images/blog/a1.png'
import blogImage2 from '~/assets/images/blog/a2.png'
import blogImage3 from '~/assets/images/blog/a3.png'
import blogImage4 from '~/assets/images/blog/a4.png'
import blogImage5 from '~/assets/images/blog/a5.png'
import blogImage6 from '~/assets/images/blog/a6.png'

const blogs = ref([
  {
    id: 1,
    image: blogImage1,
    date: '2024/02/10',
    category: 'UI/UX 新知',
    title: 'Vision Pro 登場！Vision Pro UI/UX 設計重點大公開 (上)',
    description:
      'Vision Pro 終於在 2024 年 2 月正式開賣，距離正式發表的 2023 年 6 月，已有半年時間。這半年間，各種質疑聲不斷冒出，例如「太貴了，這是做給投資家看的產品，不能真的大量生產」、「續航力明顯不足，電池太重，不利於隨身攜帶使用」、「隔絕現實世界，會更加深世代或人際關係的隔閡」。',
    content: 'test'
  },
  {
    id: 2,
    image: blogImage2,
    date: '2023/11/20',
    category: 'UI/UX 新知',
    title: '給設計師和工程師的 Figma-Dev Mode 開發模式使用指南 (下)',
    description:
      '延續上一篇針對 Dev Mode 介紹這一篇要說的就是最複雜的「右側面板」啦！右側面板預設有兩個分頁：Inspect（偵測）, Plugins（外掛），預設開啟 Inspect。 右側面板也可以顯示 Comment，但需要先在左側面板上方點擊 對話 icon，才可以在右側面板看到所有留言紀錄。',
    content: ''
  },
  {
    id: 3,
    image: blogImage3,
    date: '2023/10/18',
    category: 'UI/UX 新知',
    title: '給設計師和工程師的 Figma-Dev Mode 開發模式使用指南 (上)',
    description:
      '身為工程師，除了精進開發技術、學習新框架、看更多的範例、刷更多的題，為了與其他團隊成員有效合作，也需要學習使用其他協作軟體，例如 Trello, Notion。 而如果是要跟設計師合作，目前最主要的就是使用 Figma了！Figma 是現在最主流的 UIUX 設計軟體，自從開創了「協作功能」之後，幾乎就是把 Adobe XD 和 Sketch 遠遠甩在後頭！',
    content: ''
  },
  {
    id: 4,
    image: blogImage4,
    date: '2023/09/20',
    category: '數位產品設計',
    title: '虛擬實境 (VR) 介面設計對使用者沈浸感影響的研究',
    description:
      '在當今數位科技的快速發展下，虛擬實境（VR）技術日益受到關注。VR技術為使用者提供了身臨其境的體驗，並在多個領域中得到應用，如遊戲、教育、醫療等。然而，要實現真正的沈浸感需要考慮多個因素，其中介面設計是至關重要的一環。本研究旨在探討不同介面設計對使用者在虛擬環境中的沈浸感的影響，以期為優化VR技術的使用者體驗提供參考。',
    content: ''
  },
  {
    id: 5,
    image: blogImage5,
    date: '2023/08/10',
    category: '平面設計',
    title: '想打到目標受眾？先讓設計師跟你都瞭解他們痛在哪！',
    description:
      '一個準備完整的案主，會在發案之前，先準備好這個設計案的目標、受眾、主要功能、參考資料，然後交給設計師參考、發想、研究、使用。有些產品的目標受眾很明確，譬如一個比價 App，受眾目標的特徵可能有：年齡層廣、會使用線上購物、手機使用時間長。 但可以比價的東西實在太多了，若五花八門的商品都要拉進去，設計上需要建立非常多的目錄階層、制定非常多種的產品詳細頁面版型等等。',
    content: ''
  },
  {
    id: 6,
    image: blogImage6,
    date: '2023/07/03',
    category: '前端開發',
    title: 'React vs. Vue，哪種前端框架比較好用？從三大面向談起',
    description:
      '在當今快速發展的前端開發領域中，React和Vue被廣泛認為是兩個最受歡迎和強大的前端框架之一。然而，對於開發人員來說，選擇適合自己的框架可能是一個具有挑戰性的決定。本文將從三個主要面向探討React和Vue：開發效率、性能和生態系統。通過深入比較和分析這些方面，我們將試圖回答一個關鍵問題：React和Vue中哪種前端框架更加適用？這將有助於開發人員更好地理解兩者之間的優勢和劣勢！',
    content: ''
  }
])

let mainSwiper: any
let onSwiper1: (swiper: any) => void

if (process.client) {
  onSwiper1 = (swiper: any) => {
    mainSwiper = swiper
  }
}
onMounted(() => {
  nextTick(() => {
    mainSwiper.update() // 強制更新 Swiper，確保新的尺寸被正確計算
  })
})
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

      <div class="flex flex-col items-center justify-center px-5 lg:items-start lg:pl-6 lg:pr-0">
        <h2 class="mb-6 text-[32px] text-[#3B3B3B] lg:text-[40px]">Hi！我是 2fish</h2>
        <p class="mb-4 text-[20px] leading-[32px] text-[#5B5B5B]">
          具有 1 年經驗的<span class="b-line">前端工程師</span> & <span class="b-line">UIUX 設計師</span>，技術雙修並行，熱衷於優化使用者的網頁體驗
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
          <NuxtLink to="/portfolio" class="mb-card-btn hover-opacity-80">
            完整介紹 <Icon name="material-symbols:arrow-right-alt-rounded" size="24"></Icon>
          </NuxtLink>
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
          <NuxtLink to="/portfolio" class="mb-card-btn hover-opacity-80">
            完整介紹 <Icon name="material-symbols:arrow-right-alt-rounded" size="24"></Icon>
          </NuxtLink>
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
          <NuxtLink to="/portfolio" class="mb-card-btn hover-opacity-80">
            完整介紹 <Icon name="material-symbols:arrow-right-alt-rounded" size="24"></Icon>
          </NuxtLink>
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
        <NuxtLink to="/service" class="card-btn hover-opacity-80">
          詳細內容與合作流程 <Icon name="material-symbols:arrow-right-alt-rounded" size="24"></Icon>
        </NuxtLink>
      </div>
    </section>

    <!-- * blog -->
    <section class="py-20 lg:py-[120px]">
      <title-component title="精選文章" class="mb-10 lg:mb-20"></title-component>

      <!-- mb 顯示 3EA + btn -->
      <div class="lg:hidden flex flex-col gap-12 px-4">
        <div v-for="(item, i) of blogs.slice(0, 3)" class="flex h-full w-full flex-col bg-white" :key="i">
          <div class="pic overflow-hidden rounded-lg max-h-[400px]">
            <img :src="item.image" alt="portfolio image" class="pic-auto" />
          </div>
          <div class="content mt-4 grow bg-white px-2">
            <h3 class="mb-2 text-[20px] text-[#3B3B3B]">{{ item.title }}</h3>
            <div class="mt-4 flex items-center justify-between">
              <div class="bg-[#F1F1F1] px-3 py-1 text-[#3B3B3B]">{{ item.category }}</div>
              <div class="text-[#5B5B5B]">{{ item.date }}</div>
            </div>
          </div>
        </div>
        <NuxtLink to="/blog" class="card-btn hover-opacity-80">
          更多文章 <Icon name="material-symbols:arrow-right-alt-rounded" size="24"></Icon>
        </NuxtLink>
      </div>

      <!-- pc swiper -->
      <ClientOnly>
        <div
          class="relative m-auto mb-[60px] hidden h-full max-w-[1200px] lg:block"
          id="mainSwiper"
        >
          <!-- :height="400" -->
          <Swiper
            :modules="[
              SwiperAutoplay,
              SwiperEffectCreative,
              SwiperScrollbar,
              SwiperPagination,
              SwiperNavigation
            ]"
            :loop="true"
            :slides-per-view="2"
            :slides-per-group="2"
            :effect="'creative'"
            :pagination="{
              el: '.swiper-pagination',
              clickable: true
            }"
            :autoplay="{
              delay: 5000,
              disableOnInteraction: true
            }"
            :creative-effect="{
              prev: {
                shadow: false,
                translate: ['-30%', 0, -1]
              },
              next: {
                translate: ['100%', 0, 0]
              }
            }"
            @swiper="onSwiper1"
          >
            <SwiperSlide
              v-for="(item, i) of blogs"
              class="flex h-full w-full flex-col bg-white px-2"
              :key="i"
            >
              <div class="pic overflow-hidden rounded-lg">
                <img :src="item.image" alt="portfolio image" />
              </div>
              <div class="content mt-4 grow bg-white px-2">
                <h3 class="mb-2 text-[28px] text-[#3B3B3B]">{{ item.title }}</h3>
                <div class="mt-4 flex items-center justify-between">
                  <div class="bg-[#F1F1F1] px-3 py-1 text-[#3B3B3B]">{{ item.category }}</div>
                  <div class="text-[#5B5B5B]">{{ item.date }}</div>
                </div>
              </div>
            </SwiperSlide>
          </Swiper>
          <div class="swiper-pagination"></div></div
      ></ClientOnly>
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

/* swiper */
.swiper-pagination {
  text-align: center;
  line-height: 40px;
  position: absolute;
  left: 0;
  right: 0;
  bottom: -60px;
}

.swiper-pagination span {
  margin: 0 5px;
  padding: 2px 10px;
  border: 1px solid #000;
  border-radius: 10px;
  cursor: pointer;
}

/* ::v-deep .swiper-pagination-bullet {
  background: transparent;
  height: 40px;
  color: #3b3b3b;
  font-size: 24px;
  width: 40px;
  height: 40px;
  text-align: center;
  line-height: 40px;
  transition: all 0.3s ease-in-out;
  border-radius: 4px;
  margin: 0 8px !important;
}

::v-deep .swiper-pagination-bullet-active {
  background: #1e1e1e;
  color: #ffffff;
} */

@media screen and (min-width: 1024px) {
  .sec-service {
    background: url('~/assets/images/home/sec3-bg-pc.png') no-repeat center center;
    background-size: cover;
  }
}
</style>
