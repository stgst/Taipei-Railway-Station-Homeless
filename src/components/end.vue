<script setup>
import Btn from '@/components/Btn.vue'
</script>

<template>
    <div id="title" class="text-white flex justify-center h-screen overflow-y-auto">
        <div class="container mx-auto px-4 py-8 md:mt-auto w-xs md:w-md text-left text-lg max-h-screen overflow-y-auto">
            <span class="block text-2xl font-bold mb-4">3. 收尾</span>
            <span>　　睿璟：非常感謝大家與我們共度今天的 90 分鐘，參與此次的北車導覽活動。不知道大家是否還記得一開始 OA 大哥問到「無家者是否值得同情」這個問題時，我在「不值得」的地方舉起了手。</span><br><br>
            <span>　　我想，在這場活動中，與其說是同情這種上對下的情感，我更期待能以同理與理解的方式，用平等的關係去看見對方。這樣的關係，才更貼近人與人之間真實的連結。</span><br><br>
            <span>　　也希望在今天之後，大家能夠帶著平等的心態與同理的角度，去理解無家者議題、面對無家者。</span><br><br>
            <div class="relative flex justify-center mt-10 mb-10">
                <Btn />
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
