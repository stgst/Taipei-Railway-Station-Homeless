<script setup>
import Btn from '@/components/Btn.vue'
</script>

<template>
    <div id="title" class="text-white flex justify-center h-screen overflow-y-auto">
        <div class="container mx-auto px-4 py-8 md:mt-auto w-xs md:w-md text-left text-lg max-h-screen overflow-y-auto space-y-6">
        <!-- 地點 -->
        <div>
            <h2 class="text-xl font-bold mb-2">📍 導覽地點3：</h2>
            <p class="pl-4">台北車站 南一門內</p>
        </div>
        <!-- 介紹 -->
        <div>
            <h2 class="text-xl font-bold mb-2">無家者的工作與薪水：</h2>
            <p class="pl-4">
                人生百味補充：大哥大姐大多都是打零工，一天一千薪水沒有很多，可能有時候看到他們都在休息，因為有些已經工作完，並不是都沒有在工作。有些沒有在工作的可能是精神疾病或是年紀比較大等因素。OA大哥一開始的工作是去舉牌。<br>
                OA大哥：打零工也有好處，每天都會有薪水，很吸引無家者  老闆們不發愁找不到人，因為很多人都想要打零工。另外，有些人會去做粗工，像是到工地搬磚頭之類的，薪水就會比較高。
            </p>
        </div>
        <div class="flex justify-center">
                <div class="grid grid-cols-1 sm:grid-cols-2 gap-4">                    
                    <img src="../assets/img/人生百味補充.JPG" alt="圖片2" class="w-full h-auto rounded-lg shadow-md object-cover max-w-xs" />
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