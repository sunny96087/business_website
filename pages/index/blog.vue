<!-- blog -->
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

// 目前選擇分類
const selectedCategory = ref('')
// 目前頁面
const isMainPage = ref(true)
// 目前閱讀文章
const currentArticleId = ref<number | null>(null)

const filteredBlogs = computed(() => {
  if (!selectedCategory.value) return blogs.value
  return blogs.value.filter((blog) => blog.category === selectedCategory.value)
})

function handleArticleClick(id) {
  currentArticleId.value = id
  isMainPage.value = false
}

// 定義方法
function selectCategory(category) {
  selectedCategory.value = category
  isMainPage.value = true
}
</script>

<template>
  <section class="pb-[40px] lg:pb-[80px]" v-if="isMainPage">
    <title-component title="部落格" class="pt-20 lg:pt-[120px]"></title-component>
    <p class="mt-4 text-center text-[#919191] lg:mt-6">不定期分享技術文章</p>
  </section>

  <section class="flex flex-col lg:mx-auto lg:max-w-[1200px] lg:flex-row lg:gap-6">
    <!-- * mb - bar -->
    <div
      class="sticky left-0 right-0 top-[80px] overflow-x-auto bg-[#FAFAFA] px-3 py-5 text-[#5B5B5B] lg:hidden"
    >
      <div class="flex gap-8 px-3 sm:justify-center">
        <button
          class="mb-type-btn shrink-0"
          @click="selectCategory('')"
          :class="selectedCategory === '' ? 'mb-type-btn-focus' : ''"
        >
          全部文章
        </button>
        <button
          class="mb-type-btn shrink-0"
          @click="selectCategory('前端開發')"
          :class="selectedCategory === '前端開發' ? 'mb-type-btn-focus' : ''"
        >
          前端開發
        </button>
        <button
          class="mb-type-btn shrink-0"
          @click="selectCategory('UI/UX 新知')"
          :class="selectedCategory === 'UI/UX 新知' ? 'mb-type-btn-focus' : ''"
        >
          UI/UX 新知
        </button>
        <button
          class="mb-type-btn shrink-0"
          @click="selectCategory('數位產品設計')"
          :class="selectedCategory === '數位產品設計' ? 'mb-type-btn-focus' : ''"
        >
          數位產品設計
        </button>
        <button
          class="mb-type-btn shrink-0"
          @click="selectCategory('平面設計')"
          :class="selectedCategory === '平面設計' ? 'mb-type-btn-focus' : ''"
        >
          平面設計
        </button>
      </div>
    </div>

    <!-- * Main article -->
    <div v-if="isMainPage" class="flex grow flex-col gap-10 px-8 py-10">
      <div
        v-for="blog in filteredBlogs"
        :key="blog.id"
        @click="handleArticleClick(blog.id)"
        class="flex flex-col gap-4 text-[#3B3B3B] lg:flex-row"
      >
        <div
          class="pic flex max-h-[320px] items-center justify-center overflow-hidden rounded-lg lg:min-w-[30%]"
        >
          <img :src="blog.image" alt="Blog Image" class="pic-auto" />
        </div>
        <div class="flex flex-col px-2">
          <div class="mb-4 flex items-center justify-between lg:justify-start lg:gap-4">
            <p class="text-[#5B5B5B]">{{ blog.date }}</p>
            <p class="rounded-[16px] bg-[#F1F1F1] px-3 py-1">{{ blog.category }}</p>
          </div>
          <h2 class="mb-3 text-[20px]">{{ blog.title }}</h2>
          <p class="text-gray-700">{{ blog.description }}</p>
        </div>
      </div>
    </div>
    <!-- * 內頁 -->
    <div v-else class="grow px-4 lg:pr-10 lg:pl-8 py-8">
      <div v-for="blog in filteredBlogs" :key="blog.id">
        <div v-if="currentArticleId === blog.id">
          <!-- 顯示對應文章的內容 -->
          <div class="flex items-center justify-between text-[#919191] md:justify-start md:gap-2">
            <p>{{ blog.category }}</p>
            <span class="hidden md:block">/</span>
            <p>{{ blog.date }}</p>
          </div>
          <h2 class="mt-4 text-center text-[24px] text-[#3B3B3B] lg:mt-10 lg:text-[32px] lg:text-left">
            {{ blog.title }}
          </h2>
          <p class="mt-4 text-[#3B3B3B] lg:mt-6 lg:text-[24px]">{{ blog.description }}</p>
          <!-- 其他文章內容 -->

          <!-- * 特別內容 -->
          <!-- <div v-if="currentArticleId === 1 " class="">spppppp</div> -->
        </div>
      </div>
      <!-- 內文資料不夠多, 先都顯示一樣的資料 -->
      <div class="mb-10 mt-6 flex flex-col gap-8 text-[20px] text-[#3B3B3B] lg:mb-20 lg:mt-[64px] lg:gap-10">
        <p>
          在當今數位科技的快速發展下，虛擬實境（VR）技術日益受到關注。VR技術為使用者提供了身臨其境的體驗，並在多個領域中得到應用，如遊戲、教育、醫療等。然而，要實現真正的沈浸感需要考慮多個因素，其中介面設計是至關重要的一環。本研究旨在探討不同介面設計對使用者在虛擬環境中的沈浸感的影響，以期為優化VR技術的使用者體驗提供參考。
        </p>
        <div>
          <p class="mb-4 text-[24px]">大眾看法</p>
          <p>
            虛擬實境技術近年來受到越來越多人的關注和接受。人們對VR技術的潛力持樂觀態度，認為它能夠提供全新的體驗和娛樂方式，並在教育、訓練等領域中有著廣泛的應用前景。然而，也有一些人擔心虛擬實境技術的成熟度和可靠性，對其潛在風險抱有顧慮。
          </p>
        </div>
        <div>
          <p class="mb-4 text-[24px]">現行產品</p>
          <p>
            目前市面上有許多虛擬實境產品，如Vision Pro、Oculus Rift、HTC Vive、PlayStation
            VR等。這些產品在硬件性能、軟件支持和使用者體驗等方面存在差異，而介面設計是影響使用者體驗的重要因素之一。不同的介面設計可以影響使用者的操作方式、感知真實度以及沈浸感。
          </p>
        </div>
        <div>
          <p class="mb-4 text-[24px]">技術創新</p>
          <p>
            隨著硬件技術的不斷進步，VR設備的性能和功能也在不斷提升。高解析度的顯示器、感應器、追蹤技術等創新技術的應用，使得虛擬實境的感知和互動性能夠更加真實和流暢。然而，技術創新也帶來了一些挑戰，例如圖像質量、感知延遲等問題仍然存在，需要進一步解決。<br />
            技術瓶頸：儘管虛擬實境技術取得了巨大進步，但仍然存在一些技術瓶頸需要克服。例如，許多使用者報告在使用VR設備時出現眩暈和不適感，這與感知延遲和畫面模糊等問題有關。此外，虛擬實境的內容和應用也需要更多的創新和豐富，以滿足不同使用者的需求。
          </p>
        </div>
        <div>
          <p class="mb-4 text-[24px]">技術瓶頸</p>
          <p>
            儘管虛擬實境技術取得了巨大進步，但仍然存在一些技術瓶頸需要克服。例如，許多使用者報告在使用VR設備時出現眩暈和不適感，這與感知延遲和畫面模糊等問題有關。此外，虛擬實境的內容和應用也需要更多的創新和豐富，以滿足不同使用者的需求。
          </p>
        </div>
        <div>
          <p class="mb-4 text-[24px]">未來展望</p>
          <p>
            未來，虛擬實境技術將繼續向前發展。我們可以期待更加先進的硬件設備和更加豐富多彩的虛擬內容。同時，介面設計也將繼續演進，以提供更加直觀和便捷的操作方式，進一步增強使用者的沈浸感和參與感。總的來說，虛擬實境技術的未來是充滿希望和潛力的，我們期待著看到它在各個領域中的廣泛應用和發展。
          </p>
        </div>
        <p>2Fish 主筆</p>
        <!-- 上一頁 -->
        <div class="flex justify-center lg:justify-start">
          <button @click="isMainPage = true" class="border px-6 py-3 rounded-lg border-[#3B3B3B] hover-opacity-80">返回文章列表</button>
        </div>
      </div>
    </div>

    <!-- * type -->
    <div class="relative hidden min-w-[306px] bg-[#FAFAFA] p-20 lg:block">
      <div class="sticky top-[100px] flex flex-col items-start gap-8 text-[20px]">
        <button
          class="pc-type-btn"
          @click="selectCategory('')"
          :class="selectedCategory === '' ? 'pc-type-btn-focus' : ''"
        >
          全部文章
        </button>
        <button
          class="pc-type-btn"
          @click="selectCategory('前端開發')"
          :class="selectedCategory === '前端開發' ? 'pc-type-btn-focus' : ''"
        >
          前端開發
        </button>
        <button
          class="pc-type-btn"
          @click="selectCategory('UI/UX 新知')"
          :class="selectedCategory === 'UI/UX 新知' ? 'pc-type-btn-focus' : ''"
        >
          UI/UX 新知
        </button>
        <button
          class="pc-type-btn"
          @click="selectCategory('數位產品設計')"
          :class="selectedCategory === '數位產品設計' ? 'pc-type-btn-focus' : ''"
        >
          數位產品設計
        </button>
        <button
          class="pc-type-btn"
          @click="selectCategory('平面設計')"
          :class="selectedCategory === '平面設計' ? 'pc-type-btn-focus' : ''"
        >
          平面設計
        </button>
      </div>
    </div>
  </section>
</template>
<style scoped>
/* 隱藏水平滑動條 */
.overflow-x-auto::-webkit-scrollbar {
  display: none;
}

.pc-type-btn {
  @apply shrink-0 transform border-b-2 border-transparent p-1 duration-200;
}
.pc-type-btn:hover {
  @apply border-[#1E1E1E]  text-[#1E1E1E];
}
.pc-type-btn-focus {
  @apply border-[#1E1E1E]  text-[#1E1E1E];
}

.mb-type-btn {
  @apply border-b border-transparent p-1;
}
.mb-type-btn-focus {
  @apply border-[#1E1E1E]  text-[#1E1E1E];
}
</style>
