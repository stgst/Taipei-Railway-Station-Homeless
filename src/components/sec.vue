<script setup>
import Btn from '@/components/Btn.vue'
</script>

<template>
    <div id="title" class="text-white flex justify-center h-screen overflow-y-auto">
        <div class="container mx-auto px-4 py-8 md:mt-auto w-xs md:w-md text-left text-lg max-h-screen overflow-y-auto space-y-6">
        <!-- 地點 -->
        <div>
            <h2 class="text-xl font-bold mb-2">📍 導覽地點2：</h2>
            <p class="pl-4">
                台北車站周圍：東三門->南門->西門->北門->東門->南一門                      
            </p>
        </div>
        <!-- 介紹 -->
        <div>
            <h2 class="text-xl font-bold mb-2">無家者的生活區域</h2>
            <p class="pl-4">
                從東三門出發，OA大哥提到前面的黃色小火車，曾經有無家者在裡面睡覺。<br>圖片中的黑色袋子是無家者的個人物品，北車會幫忙保管，避免環境髒亂。
            </p>
            <div class="flex justify-center">
                <div class="grid grid-cols-1 sm:grid-cols-2 gap-4">
                    <img src="../assets/img/無家者生活區域3.jpeg" alt="圖片1" class="w-full h-auto rounded-lg shadow-md object-cover max-w-xs" />
                    <img src="../assets/img/無家者生活區域2.JPG" alt="圖片2" class="w-full h-auto rounded-lg shadow-md object-cover max-w-xs" />
                </div>
            </div>
        </div>
        <!-- 內文 -->
        <div>
            <h2 class="text-xl font-bold mb-2">接下來，帶大家認識台北車站周圍的無家者聚集區：</h2>
            <ol class="pl-8 list-decimal">
                <li>
                    <span class="block text-xl font-bold mb-2">南門：</span>
                    這裡被認為是一些角頭勢力的聚集地。
                </li>
                <br>
                <li>
                    <span class="block text-xl font-bold mb-2">南二門：</span>
                    有凹進去的地方，是一個避風避雨的地方，但通常被「大哥級」無家者佔據。此處是物資發放的第一站。
                </li>
                <div class="flex justify-center">
                    <div class="grid grid-cols-1 sm:grid-cols-2 gap-4">
                        <img src="../assets/img/南二門.jpg" alt="圖片1" class="w-full h-auto rounded-lg shadow-md object-cover max-w-xs" />                    
                    </div>
                </div>
                <br>
                <li>
                    <span class="block text-xl font-bold mb-2">西門：</span>
                    這裡是計程車上下客的地方，旅客比較多，也是物資分發的第一站，無家者在這裡坐著休息，但不能躺著。
                    無家者比較喜歡在南二門及西門，因為是物資發放的主要區域。
                </li>
                <div class="flex justify-center">
                    <div class="grid grid-cols-1 sm:grid-cols-2 gap-4">
                        <img src="../assets/img/西三門.jpg" alt="圖片1" class="w-full h-auto rounded-lg shadow-md object-cover max-w-xs" />                    
                    </div>
                </div>
                <br>
                <li>
                    <span class="block text-xl font-bold mb-2">北門：</span>
                    這裡相對安靜，是我過去喜歡睡覺的地方，因為有監視器，也比較少有酒鬼鬧事，並且警察會來巡邏，比較安全。
                </li>
                <div class="flex justify-center">
                    <div class="grid grid-cols-1 sm:grid-cols-2 gap-4">
                        <img src="../assets/img/北三門.jpg" alt="圖片1" class="w-full h-auto rounded-lg shadow-md object-cover max-w-xs" />                    
                    </div>
                </div>
                <br>
                <li>
                    <span class="block text-xl font-bold mb-2">東門：</span>
                    這裡曾是有人睡覺的地點，現在不行，但固定有愛心團體在這裡發放便當。
                </li>
                <br>
                <li>
                    <span class="block text-xl font-bold mb-2">南一門：</span>
                    有許多黑色塑膠袋事無家者的大型行李，無家者早上收行李，晚上領行李，為了整潔乾淨，早上會有社會局大哥搬到西門的地方，晚上會搬回南一門。
                    搬行李的大哥也是無家者。
                    參與者問是每天都會搬嗎？   人生百味回答：是，有些搬行李的大哥也是無家者。
                </li>
                <div class="flex justify-center">
                    <div class="grid grid-cols-1 sm:grid-cols-2 gap-4">
                        <img src="../assets/img/南一門.jpeg" alt="圖片1" class="w-full h-auto rounded-lg shadow-md object-cover max-w-xs" />                    
                    </div>
                </div>
            </ol>
        </div>
        <div>
            <h2 class="text-xl font-bold mb-2">生活中的風險</h2>
            <p class="pl-4">
                在無家者的生活中，風險無處不在。我曾在店門口睡覺時，發現有人摸我，而那是個男生；也曾在公園外被人用美工刀割開背包偷錢。這種生活，充滿了不確定性。
                而在台北車站附近，還有「地盤」的概念：一些區域有潛規則，誰能睡在哪裡，什麼時候能睡，這些都有不成文的規矩。
            </p>            
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