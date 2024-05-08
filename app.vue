<template>
  <div>
    <NuxtPage />
    <!-- <navbar />
    <NuxtLayout>
      <Slidebar />
    </NuxtLayout> -->
    <ToastTool class="z-50" />
    <CustomDialog />
    <LoadingTool />
  </div>
</template>

<script setup>
useHead({
  title: '品牌形象網站',
  titleTemplate: (title) => (title ? `${title} - 2fish` : '2fish'),
  htmlAttrs: {
    lang: 'zh-TW'
  },
  // meta: [
  //   {
  //     name: 'description',
  //     content: '歡迎來到使用 Nuxt 3 開發的社群網站 - Chat!，本網站僅作為參加六角 Node.js 入門班學習使用'
  //   },
  //   { name: 'twitter:title', content: 'Nuxt 3 社群網站 - Chat!' },
  //   {
  //     name: 'twitter:description',
  //     content: '歡迎來到使用 Nuxt 3 開發的社群網站 - Chat!，本網站僅作為參加六角 Node.js 入門班學習使用'
  //   },
  //   { name: 'twitter:image', content: 'https://i.imgur.com/AVNujNC.png' },
  //   { property: 'og:type', content: 'website' },
  //   { property: 'og:site_name', content: 'Chat!' },
  // ],
  link: [
    {
      rel: 'icon',
      href: '/post.png'
    }
  ]
})
</script>