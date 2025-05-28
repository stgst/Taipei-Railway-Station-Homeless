<script setup>
import Btn from '@/components/Btn.vue'
</script>

<template>
    <div id="title" class="text-white flex justify-center h-screen overflow-y-auto">
        <div class="container mx-auto px-4 py-8 md:mt-auto w-xs md:w-md text-left text-lg max-h-screen overflow-y-auto space-y-6">
       
        
        <!-- 內文 -->
        <div>
            <ol class="pl-8 list-decimal">
                <li>
                    <span class="block text-xl font-bold mb-2">現實生活：</span>
                    無家者的生活看似困難，但長時間習慣後，反而會成為一種「舒適圈」。當一個人發現即使不工作也能生存時，改變的動力就會變得微弱。我自己也曾經經歷過這種生活：
                    有一次，我連續一週沒有飯吃，只能靠喝水度日，餓了就睡。最後，我使用手機上網查詢，在教會找到免費的食物，一天提供兩餐，從那時起便過著「吃飽睡、睡飽吃」的生活。當你對未來不再有期望，只求生存，這樣的生活似乎也就變得「足夠」。
                    而且，當我開始有一點收入後，會優先拿來滿足基本需求，比如買飲料。而在有了穩定的收入後，我選擇去網咖過夜，每晚四個小時180元，避免了露宿街頭。這種「稍微好一點」的生活，讓我有了一種表面上的安定。
                </li>
                <br>
                <li>
                    <span class="block text-xl font-bold mb-2">如何有效協助無家者：</span>
                    幫助無家者，並不僅僅是給食物或金錢。更重要的是思考：「什麼樣的幫助才能真正改變他們的生活？」
                </li>
                <br>
                <!-- 這邊也可以設計留言區 -->
                <li>
                    <span class="block text-xl font-bold mb-2">OA大哥：請問大家最重要的是什麼？例如銀行可以領錢</span>
                    參與者回應：是住宿嗎？是飲水機？是廁所？還是有穩定收入的機會？
                    實際上，對無家者來說，最缺乏的是廁所。以台鐵周邊為例，半夜12點到4點期間廁所會關閉，無家者只能到很遠的地方上廁所，如二二八公園、中華路，甚至只能就地解決。在外面的石椅附近常常會有人就地解決，就會有很重的尿騷味，周邊都會定期用高壓水槍清洗，那個尿騷味才減少，但這也僅是緩解之道。
                    南門有一些樹跟圍欄，那個地方很多人會在台階、樹周圍可以坐的圍欄（提醒大家以後來到這邊要不要坐下，可以自行評估）隨地大小便。
                    以前客運站24小時都有廁所，但因為在這邊生活部分的人沒有愛惜使用，後來客運站才決定不開放使用。我曾提議過在台鐵附近設立臨時廁所，但台鐵沒有後續回應，也不了了之。
                </li>
                <br>
                <li>
                    <span class="block text-xl font-bold mb-2">OA大哥：請問大家會帶衛生紙嗎？</span>
                    我不知道在女廁會不會發生，就是廁所的隔板有一個個洞，男生廁所的很誇張，我感到不可思議，有人會用打火機燒塑膠隔板，來偷窺別人，所以我都會用衛生紙堵住這些洞。
                </li>
                <br>
                <li>
                    <span class="block text-xl font-bold mb-2">OA大哥：請問大家有被偷過錢嗎？</span>
                    OA大哥：之前剛來的時候在外面的躺椅睡覺，睡得太熟以大字型睡覺，都沒發現褲子口袋的錢包被偷走，有一位老人家用小刀滑開口袋，有一個個不連續的開孔，幸好，我有把錢分開放的習慣，像是藏在鞋子裡，或其他地方。所以，以後睡覺時，會側睡將錢包夾在兩腿之間，提醒大家將錢分開放。
                </li>
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