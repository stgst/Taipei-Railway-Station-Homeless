<script setup>
import Btn from '@/components/Btn.vue'
</script>

<template>
    <div id="title" class="text-white flex justify-center h-screen overflow-y-auto">
        <div class="container mx-auto px-4 py-8 md:mt-auto w-xs md:w-md text-left text-lg max-h-screen overflow-y-auto space-y-6">
        <!-- 地點 -->
        <div>
            <h2 class="text-xl font-bold mb-2">📍 導覽地點1：</h2>
            <p class="pl-4">台北車站 東三門</p>
        </div>
        <!-- 介紹 -->
        <div>
            <h2 class="text-xl font-bold mb-2">📝 介紹：</h2>
            <p class="pl-4">
                大家好，歡迎來到本次線上展覽，感謝各位的參與。我是這次展覽的籌備人，非常榮幸能夠與「人生百味」合作，透過這個線上平台，帶大家一同認識無家者的生活世界。我們希望這場展覽不只是帶來觀看的體驗，更邀請大家從不同的角度理解無家者的處境，而不僅僅停留在同情上。
            </p>
        </div>
        <!-- 內文 -->
        <div>
            <h2 class="text-xl font-bold mb-2">📖 內文：</h2>
            <p class="pl-4">
                OA大哥：我自己成為無家者還不到一年，對於在外流浪的生活經驗也相對有限。不過，正因為如此，我更想把這段期間所見所聞、所感所想分享給大家。
                首先，想請大家思考：
            </p>
            <br>
            <ol class="pl-8">
                <li>如何得知這個線上展覽以及為何會想參展</li>
                <li>你對無家者有什麼樣的好奇？</li>
                <li>你認為無家者值得同情嗎？</li>
            </ol>
            <!-- 這個地方可以寫個後端留言 -->
            <br>
            <p class="pl-4">
                其實，每個人對無家者的看法都不同，這並無對錯之分。但很多時候，我們只是看見一個人衣衫襤褸，便心生同情，卻沒有思考過他們過去的故事。這種「可憐而幫助」的心態，有時候反而無法真正改變他們的處境。
            </p>
            <br>
            <ol class="pl-8 list-decimal">
                <li>現實生活：<br>無家者的生活看似困難，但長時間習慣後，反而會成為一種「舒適圈」。當一個人發現即使不工作也能生存時，改變的動力就會變得微弱。我自己也曾經經歷過這種生活：
                有一次，我連續一週沒有飯吃，只能靠喝水度日，餓了就睡。最後，我使用手機上網查詢，在教會找到免費的食物，一天提供兩餐，從那時起便過著「吃飽睡、睡飽吃」的生活。當你對未來不再有期望，只求生存，這樣的生活似乎也就變得「足夠」。
                而且，當我開始有一點收入後，會優先拿來滿足基本需求，比如買飲料。而在有了穩定的收入後，我選擇去網咖過夜，每晚四個小時180元，避免了露宿街頭。這種「稍微好一點」的生活，讓我有了一種表面上的安定。
                </li>
                <li>你對無家者有什麼樣的好奇？</li>
                <li>你認為無家者值得同情嗎？</li>
            </ol>
        </div>
        <!-- 圖片區塊 -->
            <div>
                <h2 class="text-xl font-bold mb-2">🖼️ 圖片：</h2>
                <div class="grid grid-cols-1 sm:grid-cols-2 md:grid-cols-3 gap-4">
                <!-- 圖片1 -->
                <img src="../assets/img/東三門1.jpg" alt="圖片1" class="w-full h-auto rounded-lg shadow-md object-cover" />
                <!-- 圖片2 -->
                <img src="../assets/img/東三門2.jpg" alt="圖片2" class="w-full h-auto rounded-lg shadow-md object-cover" />
                <!-- 圖片3（可選） -->
                <img src="../assets/img/東三門3.jpg" alt="圖片3" class="w-full h-auto rounded-lg shadow-md object-cover" />
                <!-- 圖片4（若有） -->
                <!-- <img src="/img/sample4.jpg" alt="圖片4" class="w-full h-auto rounded-lg shadow-md object-cover" /> -->
            </div>
        </div>
        <!-- 按鈕 -->
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