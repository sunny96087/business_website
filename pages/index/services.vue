<!-- services -->
<script setup lang="ts">
import { showToast, openDialog, showLoading, hideLoading } from '~/store/eventBus'
</script>

<template>
  <section class="sec-service bg-white pb-[80px] lg:pb-[120px]">
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
  </section>

  <!-- * 服務流程 -->
  <section class="sec-service-items pb-[80px] lg:pb-[120px]">
    <title-component
      title="服務流程"
      color="white"
      class="pb-10 pt-20 lg:pb-[80px] lg:pt-[120px]"
    ></title-component>
    <div class="flex flex-col items-center gap-4 px-3">
      <div class="item">
        <span class="text-[48px] text-[#919191] md:text-[72px]">1</span>
        <div class="flex flex-col items-center gap-2 md:items-start">
          <p>初步接洽</p>
          <p class="">
            透過表單或其他社群軟體與我聯絡根據難易度與複雜度，後續可能需要電話/線上討論
          </p>
        </div>
      </div>
      <Icon
        title="arrow-down"
        name="material-symbols:fitbit-arrow-downward-rounded"
        size="32"
        class="text-[#5B5B5B]"
      ></Icon>
      <div class="item">
        <span class="text-[48px] text-[#919191] md:text-[72px]">2</span>
        <div class="flex flex-col items-center gap-2 md:items-start">
          <p>需求釐清</p>
          <p class="">透過訪談與問卷，解析客戶需求，並針對痛點給予實際建議</p>
        </div>
      </div>
      <Icon
        title="arrow-down"
        name="material-symbols:fitbit-arrow-downward-rounded"
        size="32"
        class="text-[#5B5B5B]"
      ></Icon>
      <div class="item">
        <span class="text-[48px] text-[#919191] md:text-[72px]">3</span>
        <div class="flex flex-col items-center gap-2 md:items-start">
          <p>委託簽約</p>
          <p class="">合約雙方用印後，即正式開始合作 可提供發票或勞務報酬單，須支付 20% 訂金</p>
        </div>
      </div>
      <Icon
        title="arrow-down"
        name="material-symbols:fitbit-arrow-downward-rounded"
        size="32"
        class="text-[#5B5B5B]"
      ></Icon>
      <div class="item">
        <span class="text-[48px] text-[#919191] md:text-[72px]">4</span>
        <div class="flex flex-col items-center gap-2 md:items-start">
          <p>版本呈現</p>
          <p class="">根據合約內容進行設計或開發</p>
        </div>
      </div>
      <Icon
        title="arrow-down"
        name="material-symbols:fitbit-arrow-downward-rounded"
        size="32"
        class="text-[#5B5B5B]"
      ></Icon>
      <div class="item">
        <span class="text-[48px] text-[#919191] md:text-[72px]">5</span>
        <div class="flex flex-col items-center gap-2 md:items-start">
          <p>來回修正</p>
          <p class="">依據合約規定之修正次數進行，次數計算以 mail 為準</p>
        </div>
      </div>
      <Icon
        title="arrow-down"
        name="material-symbols:fitbit-arrow-downward-rounded"
        size="32"
        class="text-[#5B5B5B]"
      ></Icon>
      <div class="item">
        <span class="text-[48px] text-[#919191] md:text-[72px]">6</span>
        <div class="flex flex-col items-center gap-2 md:items-start">
          <p>終版確認</p>
          <p class="">雙方同意後即為最終版</p>
        </div>
      </div>
      <Icon
        title="arrow-down"
        name="material-symbols:fitbit-arrow-downward-rounded"
        size="32"
        class="text-[#5B5B5B]"
      ></Icon>
      <div class="item">
        <span class="text-[48px] text-[#919191] md:text-[72px]">7</span>
        <div class="flex flex-col items-center gap-2 md:items-start">
          <p>結案</p>
          <p class="">客戶簽署驗收單，並於約定日期支付尾款</p>
        </div>
      </div>
    </div>
  </section>

  <!-- * 價格表 -->
  <section class="sec-price bg-white pb-[80px] lg:pb-[120px]">
    <title-component
      title="價格表"
      class="pb-10 pt-20 lg:pb-[80px] lg:pt-[120px]"
    ></title-component>

    <div class="flex flex-col items-center gap-6 xl:flex-row xl:justify-center">
      <div class="price-item">
        <div>
          <Icon
            name="material-symbols-light:design-services-outline-rounded"
            size="46"
            class="text-[#C1C1C1]"
          ></Icon>
        </div>
        <h2 class="text-nowrap text-[20px] text-[#5B5B5B] xl:text-[24px]">平面設計</h2>
        <div class="mx-2 h-[1px] w-[28px] bg-[#C1C1C1] xl:w-[19px]"></div>
        <span class="text-[20px] text-[#1E1E1E] xl:text-[32px]">6,000</span>
        <span class="text-[#5B5B5B]">起</span>
      </div>

      <div class="price-item">
        <div><Icon name="iconoir:design-nib-solid" size="46" class="text-[#C1C1C1]"></Icon></div>
        <h2 class="text-nowrap text-[20px] text-[#5B5B5B] xl:text-[24px]">UI 設計</h2>
        <div class="mx-2 h-[1px] w-[28px] bg-[#C1C1C1] xl:w-[19px]"></div>
        <span class="text-[20px] text-[#1E1E1E] xl:text-[32px]">15,000</span>
        <span class="text-[#5B5B5B]">起</span>
      </div>

      <div class="price-item">
        <div><Icon name="ph:code" size="46" class="text-[#C1C1C1]"></Icon></div>
        <h2 class="text-nowrap text-[20px] text-[#5B5B5B] xl:text-[24px]">前端開發</h2>
        <div class="mx-2 h-[1px] w-[28px] bg-[#C1C1C1] xl:w-[19px]"></div>
        <span class="text-[20px] text-[#1E1E1E] xl:text-[32px]">22,000</span>
        <span class="text-[#5B5B5B]">起</span>
      </div>
    </div>
  </section>

  <!-- * 客戶案例 -->
  <section class="sec-price bg-[#FAFAFA] pb-[80px] lg:pb-[120px]">
    <title-component
      title="客戶案例"
      class="pb-10 pt-20 lg:pb-[80px] lg:pt-[120px]"
    ></title-component>

    <div
      class="grid max-w-[1200px] grid-cols-1 gap-12 px-3 lg:mx-auto lg:grid-cols-2 lg:gap-x-6 lg:gap-y-20"
    >
      <div class="card">
        <div class="card-pic">
          <img src="~assets/images/portfolio/p4-pc.png" class="pic-auto" alt="" />
        </div>
        <div class="p-4">
          <h4 class="card-title">美美美早餐店 POS 機 UI Design</h4>
          <p class="card-desc">訂單送單一目瞭然，自動報表分析好輕鬆</p>

          <div class="card-tags">
            <div class="card-tag">UI 設計</div>
            <div class="card-tag">前端開發</div>
            <div class="card-tag">Wix</div>
          </div>
        </div>
      </div>
      <div class="card">
        <div class="card-pic">
          <img src="~assets/images/portfolio/p6-pc.png" class="pic-auto" alt="" />
        </div>
        <div class="p-4">
          <h4 class="card-title">巧克巧克形象官網設計</h4>
          <p class="card-desc">三步驟完成訂票，電腦手機都支援</p>

          <div class="card-tags">
            <div class="card-tag">UI 設計</div>
            <div class="card-tag">設計系統</div>
            <div class="card-tag">網路電商</div>
          </div>
        </div>
      </div>
      <div class="card">
        <div class="card-pic">
          <img src="~assets/images/portfolio/p5-pc.png" class="pic-auto" alt="" />
        </div>
        <div class="p-4">
          <h4 class="card-title">電影院訂票系統</h4>
          <p class="card-desc">三步驟完成訂票，電腦手機都支援</p>

          <div class="card-tags">
            <div class="card-tag">前端開發</div>
            <div class="card-tag">後端支援</div>
            <div class="card-tag">Vue</div>
          </div>
        </div>
      </div>
      <div class="card">
        <div class="card-pic">
          <img src="~assets/images/portfolio/p3-pc.png" class="pic-auto" alt="" />
        </div>
        <div class="p-4">
          <h4 class="card-title">2023 餉茶坊飲料旗艦店活動官網設計</h4>
          <p class="card-desc">主打水果主題，冰鎮夏天暑氣</p>

          <div class="card-tags">
            <div class="card-tag">網頁設計</div>
            <div class="card-tag">切版服務</div>
            <div class="card-tag">Javascript</div>
          </div>
        </div>
      </div>
    </div>
  </section>

  <!-- * 常見問題 -->
  <section class="sec-price bg-white pb-[80px] lg:pb-[120px]">
    <title-component
      title="常見問題"
      class="pb-10 pt-20 lg:pb-[80px] lg:pt-[120px]"
    ></title-component>

    <div class="px-6  flex flex-col lg:max-w-[90%] lg:ml-auto  lg:overflow-x-scroll gap-6 lg:flex-row ">
      <div class="qa-item">
        <p class="text-[20px] text-[#3B3B3B] lg:text-[24px]">時程很趕的話可以加快作業嗎？</p>
        <p class="text-[#5B5B5B] lg:text-[20px]">
          每提早一天，只要支付總報價的 5%，我們即會視為急件為您趕工！
        </p>
      </div>

      <div class="qa-item">
        <p class="text-[20px] text-[#3B3B3B] lg:text-[24px]">白天可以開會討論嗎？</p>
        <p class="text-[#5B5B5B] lg:text-[20px]">每週一三五的白天，可以約定開會時間！</p>
      </div>

      <div class="qa-item">
        <p class="text-[20px] text-[#3B3B3B] lg:text-[24px]">有實際開發的網站可以參考嗎？</p>
        <p class="text-[#5B5B5B] lg:text-[20px]">
          請填寫表單或來信索取，部分合作有簽保密協定，無法於網路上公開喔。
        </p>
      </div>

      <div class="qa-item">
        <p class="text-[20px] text-[#3B3B3B] lg:text-[24px]">提供比稿服務嗎？</p>
        <p class="text-[#5B5B5B] lg:text-[20px]">
          只要支付費用，設計提供比稿服務，但切版與前端開發恕不提供該服務內容。
        </p>
      </div>
    </div>
  </section>
</template>
<style scoped>
.service-item {
  @apply flex h-[246px] w-[266px] flex-col items-center justify-center gap-6 self-center rounded-[16px] text-[24px] text-white;
  background: linear-gradient(315deg, #1e1e1e 0%, #1e1e1e 49%, #000000 50%);
}

.sec-service-items {
  background: linear-gradient(313deg, #1e1e1e 0%, #1e1e1e 49%, #000000 50%);
}

.item {
  @apply flex w-full flex-col items-center gap-2 rounded border border-[#919191] bg-[#3B3B3B] p-6 pb-12 text-[20px] text-white md:flex-row md:gap-8 md:px-8 md:py-6 xl:grow;
}

.price-item {
  @apply flex w-full max-w-[352px] items-center gap-2 rounded-lg bg-[#FAFAFA] px-8 py-6 text-[#5B5B5B] xl:p-8;
  box-shadow: 0px 4px 8px 0px rgba(0, 0, 0, 0.08);
}

.card-pic {
  @apply max-h-[588px] overflow-hidden rounded-lg;
}

.card-title {
  @apply text-[20px] text-[#3B3B3B] lg:text-[28px];
}

.card-desc {
  @apply mb-4 mt-2 text-[#919191] lg:mb-6;
}

.card-tags {
  @apply flex gap-2;
}

.card-tag {
  @apply rounded-[16px] bg-[#F1F1F1] p-1 px-3 text-[#3B3B3B];
}

.qa-item {
  @apply flex flex-col items-start gap-4 rounded-lg border border-[#E9E9E9] p-6 w-full lg:min-w-[478px];
}
</style>
