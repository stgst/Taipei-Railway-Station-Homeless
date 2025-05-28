<script setup>
import Btn from '@/components/Btn.vue'
</script>

<template>
    <div id="title" class="text-white flex justify-center h-screen overflow-y-auto">
        <div class="container mx-auto px-4 py-8 md:mt-auto w-xs md:w-md text-left text-lg max-h-screen overflow-y-auto space-y-6">
        <!-- 地點 -->
        <div>
            <h2 class="text-xl font-bold mb-2">📍 導覽地點5：</h2>
            <p class="pl-4">
                台北車站：東森地下街                  
            </p>
        </div>      
        <!-- 內文 -->
        <div>
            <h2 class="text-xl font-bold mb-2">OA大哥介紹＋問答：</h2>
            <ol class="pl-8 list-decimal">
                <li>
                    <span class="block text-xl font-bold mb-2">無家者的核心問題</span>
                    無家者並非完全沒有工作，事實上，大部分都有在打零工，如搬磚、代排隊等。但收入無法負擔房租，而台北的房價高，生活成本也高。即使有收入，扣除日常開銷後所剩無幾，無法累積資本改變現狀。
                </li>
                <!-- 可以在這加上留言系統 -->
                <br>
                <li>
                    <span class="block text-xl font-bold mb-2">參與者問：請問政府會有補助嗎？</span>
                    OA大哥：有些人也曾申請過政府的急難救助金，但如果戶籍不在台北，便無法在這裡領取。這種制度也使得許多無家者即便來台北工作，卻無法獲得實際的援助。像是我之前在臺北有申請過，但工作人員說我的戶籍在雲林不是台北，所以無法申請台北的，只能回到雲林申請，讓我感到不解，因為現在資訊流通，電腦裡也有我的資料，為什麼不能用調閱的呢？而且台北的資源最豐富，雲林相對匱乏，這樣不就無法實際幫助到了。
                </li>   
                <div class="flex justify-center">
                    <div class="grid grid-cols-1 sm:grid-cols-2 gap-4">
                        <img src="../assets/img/東森街問答一.jpg" alt="圖片1" class="w-full h-auto rounded-lg shadow-md object-cover max-w-xs" />                
                        <img src="../assets/img/東森街問答二.jpg" alt="圖片1" class="w-full h-auto rounded-lg shadow-md object-cover max-w-xs" />                
                    </div>
                </div>             
            </ol>
        </div>
        <!-- 按鈕a -->
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