<script setup>
import Btn from '@/components/Btn.vue'
</script>

<template>
    <div id="title" class="text-white flex justify-center h-screen overflow-y-auto">
        <div class="container mx-auto px-4 py-8 md:mt-auto w-xs md:w-md text-left text-lg max-h-screen overflow-y-auto space-y-6">
        <!-- 地點 -->
        <div>
            <h2 class="text-xl font-bold mb-2">📍 導覽地點4：</h2>
            <p class="pl-4">
                台北車站：大廳                   
            </p>
        </div>
        <!-- 介紹 -->
        <div>
            <h2 class="text-xl font-bold mb-2">北車假日的大廳環境</h2>
            <p class="pl-4">
                今天是假日，所以會有外籍移工聚集在此處休息、聊天。沒有位置能靠牆坐下，讓參與者體驗坐著睡覺的感覺。
            </p>
            <div class="flex justify-center">
                <div class="grid grid-cols-1 sm:grid-cols-2 gap-4">
                    <img src="../assets/img/大廳一.jpg" alt="圖片1" class="w-full h-auto rounded-lg shadow-md object-cover max-w-xs" />
                    <img src="../assets/img/大廳二.JPG" alt="圖片2" class="w-full h-auto rounded-lg shadow-md object-cover max-w-xs" />
                </div>
            </div>
        </div>
        <!-- 內文 -->
        <div>
            <h2 class="text-xl font-bold mb-2">OA大哥介紹＋閒聊：</h2>
            <ol class="pl-8 list-decimal">
                <li>
                    <span class="block text-xl font-bold mb-2">OA大哥：請問大家有坐著睡覺的經驗嗎？</span>
                    現場大部分人搖頭，大多數人沒試過
                </li>
                <!-- 可以在這加上留言系統 -->
                <br>
                <li>
                    <span class="block text-xl font-bold mb-2">現場參與者問OA大哥問題：</span>
                    參與者問：大家會搶位置嗎？<br>
                    OA大哥：不會，其實是公共禮儀，而且會有警察管理，也不太能鬧事，雖然只是暫時性管理，因為北車範圍太大沒辦法有效管理，只能暫時防止其他人被騷擾。
                    <br>
                    <br>
                    參與者問：此處可以過夜嗎？<br>
                    OA大哥：只有在特殊節日時才可以躺著過夜，平常大廳會做兩次清掃，一次是中午，另一次是半夜十二點多，所以在半夜十二點時，台北車站的工作人員會開始趕人。
                    <br>
                </li>
            </ol>
        </div>
        <div>
            <h2 class="text-xl font-bold mb-2">十年台北人都不一定知道的北車的秘密</h2>
            <p class="pl-4">
                OA大哥：北車整點時會播放台灣傳統民謠「丟丟銅仔」(有興趣的可以去北車聽聽看，下面簡單丟張圖片)
            </p>            
            <div class="flex justify-center">
                <div class="grid grid-cols-1 sm:grid-cols-2 gap-4">
                    <img src="../assets/img/傳統民謠.jpg" alt="圖片1" class="w-full h-auto rounded-lg shadow-md object-cover max-w-xs" />                
                </div>
            </div>
        </div>
        <div>
            <h2 class="text-xl font-bold mb-2">往東森街上的閒聊</h2>
            <ol class="pl-8 list-decimal">
                <li>
                    <span class="block text-xl font-bold mb-2">參與者問：請問大哥什麼時候來台北的？</span>
                    OA大哥：其實我一直都在，原本在台北租房子，後來因為錢花光了，也沒有什麼慾望，想待在舒適圈，才開始流浪。之前有待在seven-eleven一個月，有被警察關心過，一個月後就離開此處，沒有再待在便利商店過。
                </li>            
                <li>
                    <span class="block text-xl font-bold mb-2">參與者問：大哥你認為成為無家者的核心因素是什麼？</span>
                    OA大哥：我不太確定別人的，以我的情況來說是因為心態，像是我先前講的一樣，只想待在舒適圈，無欲無求，對生活沒有動力及慾望，所以我成為無家者。
                </li>            
            </ol>
            <div class="flex justify-center">
                <div class="grid grid-cols-1 sm:grid-cols-2 gap-4">
                    <img src="../assets/img/往東森街上的閒聊一.jpg" alt="圖片1" class="w-full h-auto rounded-lg shadow-md object-cover max-w-xs" />                
                    <img src="../assets/img/往東森街上的閒聊二.jpg" alt="圖片1" class="w-full h-auto rounded-lg shadow-md object-cover max-w-xs" />                
                </div>
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