<script setup lang="ts">
import { APIStore } from '~/store/apiService'
const store = APIStore()
import { showToast, openDialog, showLoading, hideLoading } from '~/store/eventBus'
const router = useRouter()

const menu = ref(false)

const menuOpen = ref(false)

const toggleMenu = () => {
  menuOpen.value = !menuOpen.value
}
</script>

<template>
  <div class="nav-bg sticky top-0 z-20 border-b border-gray-200 py-5">
    <div class=" m-auto flex max-w-[1200px] items-center justify-between px-6">
      <nuxtLink to="/" class="paytone-one-regular text-[26px]">2Fish</nuxtLink>

      <div class="items-center justify-center gap-10 hidden lg:flex">
        <nuxtLink to="/" class="nav-item-pc" exact-active-class="font-medium">首頁</nuxtLink>
        <nuxtLink to="/portfolio" class="nav-item-pc" exact-active-class="font-medium">作品集</nuxtLink>
        <nuxtLink to="/services" class="nav-item-pc" exact-active-class="font-medium">服務項目</nuxtLink>
        <nuxtLink to="/blog" class="nav-item-pc" exact-active-class="font-medium">部落格</nuxtLink>
        <nuxtLink to="/connection" class="nav-item-pc" exact-active-class="font-medium">聯絡我</nuxtLink>
      </div>
      <div></div>
      <!-- mb menu -->
      <button @click="toggleMenu" class="z-20 lg:hidden">
        <div class="hamburger" >
          <div></div>
          <div></div>
          <div></div>
        </div>
      </button>
    </div>

    <transition name="slide">
      <div v-show="menuOpen" class="fixed inset-0 top-[80px] h-screen z-10 bg-black bg-opacity-20">
        <div
          class="menu absolute left-0 top-0 flex w-full flex-col items-center bg-white py-6 shadow-lg"
          
        >
          <nuxtLink to="/" class="nav-item-mb" exact-active-class="bg-slate-100">首頁</nuxtLink>
          <nuxtLink to="/portfolio" class="nav-item-mb" exact-active-class="bg-slate-100">作品集</nuxtLink>
          <nuxtLink to="/services" class="nav-item-mb" exact-active-class="bg-slate-100">服務項目</nuxtLink>
          <nuxtLink to="/blog" class="nav-item-mb" exact-active-class="bg-slate-100">部落格</nuxtLink>
          <nuxtLink to="/connection" class="nav-item-mb" exact-active-class="bg-slate-100">聯絡我</nuxtLink>
        </div>
      </div>
    </transition>
  </div>
</template>

<style scoped>
.nav-bg{
  background-color: #ffffffac;
  backdrop-filter: blur(5px);
}

.hamburger {
  width: 30px;
  height: 20px;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  cursor: pointer;
}

.hamburger div {
  width: 100%;
  height: 2px;
  background-color: #333;
  transition: all 0.3s linear;
  border-radius: 2px;
}

.hamburger.open div:nth-child(1) {
  transform: rotate(45deg) translate(3px, 7px);
}

.hamburger.open div:nth-child(2) {
  opacity: 0;
}

.hamburger.open div:nth-child(3) {
  transform: rotate(-45deg) translate(5px, -10px);
}

.menu {
  /* max-height: 0; */
  overflow: hidden;
  transition: all 0.3s ease-out;
}

.menu.open {
  /* max-height: 500px; */
  transition: all 0.3s ease-out;
}

/* 确保过渡 "进入" 状态设置为不可见，然后过渡到可见 */
.slide-enter-active,
.slide-leave-active {
  transition: opacity 0.5s ease;
}
.slide-enter-from,
.slide-leave-to {
  opacity: 0;
}
.slide-enter-to {
  opacity: 1;
}

.nav-item-pc{
  @apply leading-[28px] hover:font-medium transform duration-200;
}

.nav-item-mb{
  @apply block text-center w-full py-4 text-[20px] hover:bg-slate-100 transform duration-200;
}
</style>
