<script setup>
import { ref, computed, provide } from 'vue'
import Home from '@/components/Home.vue'
import Intro from '@/components/Intro.vue'
import Btn from '@/components/Btn.vue'

const pageID = ref(0)

// 提供 pageID 給其他元件使用
provide('pageID', pageID)

// 計算當前要顯示的元件
const currentComponent = computed(() => {
  switch(pageID.value) {
    case 0:
      return Home
    case 1:
      return Intro
    default:
      return Home
  }
})
</script>

<template>

  <div class="bg-zinc-900 w-screen h-screen flex items-center justify-center">
    <div class="container flex items-center justify-center">
      <div id="bg-wrapper" class="fixed bg-black opacity-50 w-full h-full md:w-lg"></div>
      <div id="bg" class="fixed w-full h-full md:w-lg"></div>
      <div id="app" class="w-full h-full md:w-lg">
        <component :is="currentComponent"/>
        <Btn />
      </div>
    </div>
  </div>

</template>

<style>

#bg {
  background-image: url('@/assets/img/bg.jpeg'); /* 用 @ 指定 Vite 的靜態路徑 */
  background-size: cover;
  background-position: center;
  filter: blur(1px);
  z-index: 0;
}
</style>
