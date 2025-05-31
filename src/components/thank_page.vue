<script setup>
import { inject } from 'vue'
import Btn from '@/components/Btn.vue'

const pageID = inject('pageID')

const resetExhibition = () => {
  pageID.value = 0  // 直接跳回首頁（Home頁面）
}
</script>

<template>
<!-- 感謝頁與分工表 -->
<div id="acknowledgements"
        class="text-white flex justify-center items-start sm:items-center h-auto sm:h-screen overflow-y-auto sm:overflow-hidden">
    <div class="container mx-auto px-4 py-12 sm:py-0 sm:px-8 w-full sm:w-[600px] text-left text-lg">
    <span class="block text-2xl font-bold mb-6 text-center">感謝與分工</span>

    <ul class="space-y-3">
        <li>
            <span class="font-semibold">主講人：</span>人生百味 OA大哥
        </li>
        <li>
            <span class="font-semibold">辦理成員：</span>
            <br>
            <span class="ml-4">蔡睿璟、劉穎宸、詹啟翔、張靖杭、王光晟</span>
        </li>
        <li><span class="font-semibold">合作組織：</span>人生百味</li>
        <li><span class="font-semibold">談合作：</span>蔡睿璟、劉穎宸</li>
        <li><span class="font-semibold">文案：</span>蔡睿璟、劉穎宸、詹啟翔</li>
        <li><span class="font-semibold">宣傳：</span>詹啟翔</li>
        <li><span class="font-semibold">拍攝：</span>張靖杭</li>
        <li><span class="font-semibold">記錄：</span>劉穎宸、詹啟翔、王光晟</li>
        <li><span class="font-semibold">實體走讀小獎品：</span>張靖杭</li>
        <li><span class="font-semibold">線上走讀：</span>詹啟翔、張靖杭</li>
    </ul>
    <div class="relative flex justify-center mt-10 mb-10">
        <!-- 使用自定義的按鈕樣式，但執行重新開始功能 -->
        <div id="btn" class="flex items-center justify-center">
            <button 
                class="cursor-pointer animate__animated animate__pulse animate__infinite flex flex-col items-center"
                @click="resetExhibition"
            >
                <img src="@/assets/img/btn.png" class="w-15 h-15 md:w-12 md:h-12 border-2 border-white rounded-full">
                <span class="text-white text-sm mt-2">重新觀展</span>
            </button>
        </div>
    </div>
        <div class="mt-10 text-center text-base italic text-gray-300">
            再次感謝每一位參與者與工作者，願這份理解持續延續在我們日常的視線與行動中。
        </div>
    </div>
</div>

</template>

<style>
#title {
    font-family: 'Noto Serif TC', sans-serif;
    font-weight: 600;
}

* {
    z-index: 10;
}
</style>
