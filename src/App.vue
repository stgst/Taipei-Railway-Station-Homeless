<script setup>
import { ref, computed, provide } from 'vue'
import Home from '@/components/Home.vue'
import Intro from '@/components/Intro.vue'
import first from '@/components/first.vue'
import first2 from '@/components/first2.vue'
import sec from '@/components/sec.vue'
import third from '@/components/third.vue'
import fourth from '@/components/fourth.vue'
import fifth from '@/components/fifth.vue'
import end from '@/components/end.vue'
import thank_page from '@/components/thank_page.vue'
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
    case 2:
      return first
    case 3:
      return first2
    case 4:
      return sec
    case 5:
      return third
    case 6:
      return fourth
    case 7:
      return fifth
    case 8:
      return end
    case 9:
      return thank_page
    default:
      return Home
  }
})
</script>

<template>

  <div id="bg" class="fixed bg-zinc-900 w-screen h-screen flex items-center justify-center">
    <div id="bg-wrapper" class="fixed bg-black opacity-50 w-screen h-screen"></div>
    <div class="container flex items-center justify-center">
      <div id="app" class="w-full h-full md:w-lg">
        <component :is="currentComponent"/>
      </div>
    </div>
  </div>

</template>

<style>

#bg {
  background-image: url('@/assets/img/bg.jpeg'); /* 用 @ 指定 Vite 的靜態路徑 */
  background-size: cover;
  background-position: center;
  z-index: 0;
}
</style>
