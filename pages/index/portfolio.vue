<!-- portfolio -->
<script setup lang="ts">
let mySwiper: any
let onSwiper: (swiper: any) => void

if (process.client) {
  onSwiper = (swiper: any) => {
    mySwiper = swiper
  }
}

// 定義作品集資料
import PortfolioImage1 from '~/assets/images/portfolio/p1.png'
import PortfolioImage2 from '~/assets/images/portfolio/p2.png'
import PortfolioImage3 from '~/assets/images/portfolio/p3.png'
import PortfolioImage4 from '~/assets/images/portfolio/p4.png'
import PortfolioImage5 from '~/assets/images/portfolio/p5.png'
import PortfolioImage6 from '~/assets/images/portfolio/p6.png'

const portfolioList = ref([
  {
    id: 1,
    image: PortfolioImage1,
    title: '星際旅行訂票平台',
    desc: '悠遊宇宙的夢想，從這裡開始實現',
    tags: ['網頁設計', '響應式設計', 'Bootstrap']
  },
  {
    id: 2,
    image: PortfolioImage2,
    title: '理財App',
    desc: '連動帳戶與行動支付，讓 AI 提供您最好的理財建議',
    tags: ['APP設計', 'iOS', 'React']
  },
  {
    id: 3,
    image: PortfolioImage3,
    title: '醫美診所官網',
    desc: '永保青春的秘密，從粹究開始',
    tags: ['網頁設計', '響應式設計', 'ＷordPress']
  },
  {
    id: 4,
    image: PortfolioImage4,
    title: '美美美早餐店 POS 機 UI Design',
    desc: '訂單送單一目瞭然，自動報表分析好輕鬆',
    tags: ['UI 設計', '前端開發', 'Wix']
  },
  {
    id: 5,
    image: PortfolioImage5,
    title: '電影院訂票系統',
    desc: '三步驟完成訂票，電腦手機都支援',
    tags: ['前端開發', '後端支援', 'Vue']
  },
  {
    id: 6,
    image: PortfolioImage6,
    title: '巧克巧克形象官網設計',
    desc: '三步驟完成訂票，電腦手機都支援',
    tags: ['UI設計', '設計系統', '網路電商']
  }
])
</script>

<template>
  <section class="w-full bg-[#FAFAFA] px-8 pb-20 pt-10 md:pt-20">
    <div class="flex flex-col items-center md:h-[168px] md:flex-row md:justify-center">
      <Icon name="bxs:quote-alt-left" size="56" class="text-[#E9E9E9] md:self-start"></Icon>
      <div class="text-center text-[20px] text-[#1E1E1E] md:text-[24px]">
        <p class="mb-2">讓使用者在觀賞與使用的旅程中，發現<span class="b-line">設計的價值</span></p>
        <p>而我在設計與開發的過程中，看見<span class="b-line">自己的價值</span></p>
      </div>
      <div class="hidden md:block md:self-end">
        <Icon name="bxs:quote-alt-right" size="56" class="text-[#E9E9E9]"></Icon>
      </div>
    </div>

    <div
      class="mt-10 flex flex-col items-center gap-5 px-8 md:mx-auto md:max-w-[640px] md:flex-row md:justify-center md:gap-10"
    >
      <div class="flex flex-col items-center">
        <p class="text-[#5B5B5B]">2B經驗</p>
        <div class="mt-[2px] h-[2px] w-6 bg-[#C1C1C1]"></div>
        <p class="mt-2 text-center text-[#3B3B3B]">
          內部監控系統、庫存系統、採購系統、行銷整合系統
        </p>
      </div>

      <div class="flex flex-col items-center">
        <p class="text-[#5B5B5B]">2C經驗</p>
        <div class="mt-[2px] h-[2px] w-6 bg-[#C1C1C1]"></div>
        <p class="mt-2 text-center text-[#3B3B3B]">
          跨國美妝保養電商、個人品牌網站、醫美網站、電子商務
        </p>
      </div>
    </div>
  </section>

  <!-- 作品換頁 - mb -->
  <section class="bg-white py-[80px] lg:hidden flex flex-col gap-6 px-4">
    <div class="card" v-for="item in portfolioList" :key="item.id">
      <div class="card-pic">
        <img :src="item.image" alt="portfolio image" class="pic-auto" />
      </div>
      <div class="p-4">
        <h4 class="card-title">{{ item.title }}</h4>
        <p class="card-desc">{{ item.desc }}</p>

        <div class="card-tags">
          <div class="card-tag" v-for="(tag, i) of item.tags" :key="i">{{ tag }}</div>
        </div>
      </div>
    </div>
  </section>

  <!-- 作品輪播圖 - pc -->
  <section class="hidden bg-white py-[120px] lg:block">
    <ClientOnly>
      <div class="relative m-auto mb-[60px] h-full max-w-[1200px]" id="bannerSwiper">
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
            clickable: true,
            renderBullet: (index: number, className: string) => {
              return '<span class=' + className + '>' + (index + 1) + '</span>'
            }
          }"
          :autoplay="{
            delay: 5000,
            disableOnInteraction: true
          }"
          :creative-effect="{
            prev: {
              shadow: false,
              translate: ['-20%', 0, -1]
            },
            next: {
              translate: ['100%', 0, 0]
            }
          }"
          @swiper="onSwiper"
        >
          <SwiperSlide
            v-for="(item, i) of portfolioList"
            class="flex h-full w-full flex-col bg-white px-2"
            :key="i"
          >
            <!-- <a class="item" href="#" @click.prevent="bannerLink(item)">
                <img :src="item.lURL" :alt="item.name" /> 
              </a>-->
            <!-- {{ item }} -->
            <div class="pic overflow-hidden rounded-lg">
              <img :src="item.image" alt="portfolio image" />
            </div>
            <div class="content grow bg-white p-4">
              <h3 class="mb-2 text-[28px] text-[#3B3B3B]">{{ item.title }}</h3>
              <p class="mb-6 text-[#919191]">{{ item.desc }}</p>
              <div class="flex gap-4">
                <div
                  v-for="(tag, i) of item.tags"
                  :key="i"
                  class="rounded-[16px] bg-[#F1F1F1] px-3 py-1 text-[#3B3B3B]"
                >
                  {{ tag }}
                </div>
              </div>
            </div>
          </SwiperSlide>
        </Swiper>
        <div class="swiper-pagination"></div>
        <!-- <div class="swiper-button-next" @click="mySwiper.slideNext()" id="bannerNext"></div> -->
        <!-- <div class="swiper-button-prev" @click="mySwiper.slidePrev()" id="bannerPrev"></div> -->
      </div></ClientOnly
    >
  </section>
</template>
<style scoped>
.swiper-pagination {
  text-align: center;
  line-height: 40px;
  position: absolute;
  left: 0;
  right: 0;
  bottom: -60px;
  /* background: #abc; */
}

.swiper-pagination span {
  margin: 0 5px;
  padding: 2px 10px;
  border: 1px solid #000;
  border-radius: 10px;
  cursor: pointer;
}

::v-deep .swiper-pagination-bullet {
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
}

.card-pic {
  @apply max-h-[400px] overflow-hidden rounded-lg flex justify-center items-center;
}

.card-title {
  @apply text-[20px] text-[#3B3B3B] lg:text-[28px];
}

.card-desc {
  @apply mb-4 mt-2 text-[#919191] lg:mb-6;
}

.card-tags {
  @apply flex gap-2 flex-wrap;
}

.card-tag {
  @apply rounded-[16px] bg-[#F1F1F1] p-1 px-3 text-[#3B3B3B];
}
</style>
