<script setup lang="ts">
import { APIStore } from '~/store/apiService'
const store = APIStore()
</script>

<template>
  <main class="relative min-h-screen w-full flex flex-col">
    <navbar />
    <div class="grow">
      <NuxtPage />
    </div>
    <!-- <div class="page-wrapper">
    </div> -->
    <Footer />
  </main>
</template>
<style scoped>
main {
  background: #FFFFFF;
  /* background-size: cover; */
  /* background-attachment: fixed; */
  font-family: 'Noto Sans';
}

.page-wrapper {
  /* max-width: 1200px; */
  width: 100%;
  margin: 0 auto;
  display: flex;
  /* gap: 28px; */
  /* padding: 40px 24px; */
  /* padding-bottom: 60px; */
  align-items: start;
}
</style>
