<script setup>
import { ref, onMounted, onUnmounted } from 'vue'
import Btn from '@/components/Btn.vue'

// 響應式數據
const currentIndex = ref(0)
let intervalId = null

// API URL
const API_URL = 'https://script.google.com/macros/s/AKfycbxqAegVQOC9Bt0UtXV1xds6ZAkTJYo6jTEESOvXZ1dG5-qyPJP1l1VRMeKyOegue90u/exec'

// 留言數據
const messages = ref([
    {
        id: 1,
        avatar: '../assets/img/user.png',
        text: '謝謝分享這麼真實的經歷，讓我重新思考對無家者的看法',
        name: '訪客'
    },
    {
        id: 2,
        avatar: '../assets/img/user.png',
        text: '每個人背後都有自己的故事，不應該只用表面來判斷',
        name: '訪客'
    },
    {
        id: 3,
        avatar: '../assets/img/user.png',
        text: '這個展覽很有意義，希望能改變社會對無家者的刻板印象',
        name: '訪客'
    },
    {
        id: 4,
        avatar: '../assets/img/user.png',
        text: '原來「舒適圈」不只存在於一般人的生活中...',
        name: '訪客'
    },
    {
        id: 5,
        avatar: '../assets/img/user.png',
        text: '感謝OA大哥的分享，讓我們看見不同的人生故事',
        name: '訪客'
    }
])

// 新留言輸入
const newMessage = ref('')
const isSubmitting = ref(false)

// 獲取留言
const fetchMessages = async () => {
    try {
        console.log('正在獲取留言...')
        
        // 先嘗試 cors 模式
        let response
        try {
            response = await fetch(API_URL, {
                method: 'GET',
                mode: 'cors'
            })
        } catch (corsError) {
            console.log('CORS 模式失敗，嘗試 no-cors 模式')
            // 如果 cors 失敗，嘗試 no-cors 模式
            response = await fetch(API_URL, {
                method: 'GET',
                mode: 'no-cors'
            })
        }
        
        if (!response.ok) throw new Error('獲取留言失敗')
        
        const data = await response.json()
        console.log('獲取到的留言數據:', data)
        
        if (data && Array.isArray(data)) {
            // 處理字串陣列格式 - 每個元素都是一條留言文本
            const apiMessages = data.map((text, index) => ({
                id: Date.now() + index,
                avatar: '../assets/img/user.png',
                text: text,
                name: '訪客'
            }))
            
            // 更新留言數據
            messages.value = apiMessages
            console.log('留言數據更新完成，共', apiMessages.length, '則留言')
        }
    } catch (error) {
        console.error('獲取留言出錯:', error)
        // 如果無法獲取留言，保持使用預設留言
        console.log('使用預設留言數據')
    }
}

// 開始輪播
const startCarousel = () => {
    intervalId = setInterval(() => {
        currentIndex.value = (currentIndex.value + 1) % messages.value.length
    }, 5000) // 改為3秒切換一次
}

// 停止輪播
const stopCarousel = () => {
    if (intervalId) {
        clearInterval(intervalId)
        intervalId = null
    }
}

// 添加新留言
const addMessage = async () => {
    if (newMessage.value.trim() && !isSubmitting.value) {
        isSubmitting.value = true
        
        try {
            console.log('正在提交留言:', newMessage.value.trim())
            const response = await fetch(API_URL, {
                method: 'POST',
                mode: 'no-cors',
                headers: {
                    'Content-Type': 'application/json',
                },
                body: JSON.stringify({"comment": newMessage.value.trim()})
            })
            
            console.log('Response received (no-cors mode)')
            
            newMessage.value = ''
            
            setTimeout(async () => {
                await fetchMessages()
                currentIndex.value = messages.value.length - 1
            }, 1000)
            
            stopCarousel()
            setTimeout(startCarousel, 3000)
            
            console.log('留言提交完成')
            alert('留言已提交！')
            
        } catch (error) {
            console.error('提交留言出錯:', error)
            alert(`留言提交失敗：${error.message}`)
        } finally {
            isSubmitting.value = false
        }
    }
}

const goToMessage = (index) => {
    currentIndex.value = index
    stopCarousel()
    setTimeout(startCarousel, 3000) 
}

onMounted(() => {
    fetchMessages()
    startCarousel()
})

onUnmounted(() => {
    stopCarousel()
})

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


<style scoped>
#title {
    font-family: 'Noto Serif TC', sans-serif;
    font-weight: 600;
}

* {
    z-index: 10;
}

.msg_container {
    width: 350px;
    margin: 20px auto;
    background: rgba(255, 255, 255, 0.05);
    backdrop-filter: blur(10px);
    border-radius: 16px;
    padding: 20px;
    border: 1px solid rgba(255, 255, 255, 0.1);
    box-shadow: 0 8px 32px rgba(0, 0, 0, 0.2);
}

.msg_input_area {
    display: flex;
    justify-content: center;
    align-items: center;
    gap: 8px;
    margin-bottom: 16px;
}

.msg_in {
    flex: 1;
    height: 40px;
    border-radius: 20px;
    padding: 8px 16px;
    border: 2px solid rgba(255, 255, 255, 0.2);
    font-size: 14px;
    background: rgba(255, 255, 255, 0.632);
    color: #333;
    transition: all 0.3s ease;
}

.msg_in:focus {
    outline: none;
    border-color: #4A90E2;
    box-shadow: 0 0 0 3px rgba(74, 144, 226, 0.2);
}

.msg_btn {
    background: linear-gradient(135deg, #4A90E2, #357ABD);
    color: white;
    border-radius: 20px;
    padding: 8px 16px;
    font-size: 14px;
    font-weight: 600;
    text-decoration: none;
    border: none;
    cursor: pointer;
    display: flex;
    align-items: center;
    justify-content: center;
    gap: 4px;
    transition: all 0.3s ease;
    white-space: nowrap;
}

.msg_btn:hover:not(:disabled) {
    background: linear-gradient(135deg, #357ABD, #2E6DA4);
    transform: translateY(-1px);
    box-shadow: 0 4px 12px rgba(74, 144, 226, 0.3);
}

.msg_btn:disabled {
    background: #ccc;
    cursor: not-allowed;
    opacity: 0.6;
}

.msg_card_display {
    position: relative;
    height: 120px;
    overflow: hidden;
    border-radius: 12px;
    margin-bottom: 12px;
}

.msg_card {
    display: flex;
    align-items: flex-start;
    gap: 12px;
    background: linear-gradient(135deg, rgba(255, 255, 255, 0.6), rgba(255, 255, 255, 0.5));
    border-radius: 12px;
    padding: 16px;
    color: #333;
    border: 1px solid rgba(255, 255, 255, 0.2);
    position: absolute;
    top: 0;
    left: 0;
    right: 0;
    opacity: 0;
    transform: translateY(20px);
    transition: all 0.6s cubic-bezier(0.4, 0, 0.2, 1);
    box-shadow: 0 4px 20px rgba(0, 0, 0, 0.1);
}


.msg_card.active {
    opacity: 1;
    transform: translateY(0);
    z-index: 1;
}

.avatar {
    width: 40px;
    height: 40px;
    border-radius: 50%;
    flex-shrink: 0;
    border: 2px solid rgba(255, 255, 255, 0.8);
    box-shadow: 0 2px 8px rgba(0, 0, 0, 0.1);
}

.msg_content {
    flex: 1;
    min-width: 0;
}

.msg_name {
    font-size: 12px;
    font-weight: 600;
    color: #666;
    margin-bottom: 4px;
}

.msg_text {
    font-size: 14px;
    line-height: 1.5;
    color: #333;
    word-wrap: break-word;
}

.msg_indicators {
    display: flex;
    justify-content: center;
    gap: 6px;
    margin-bottom: 12px;
}

.indicator {
    width: 8px;
    height: 8px;
    border-radius: 50%;
    border: none;
    background: rgba(255, 255, 255, 0.3);
    cursor: pointer;
    transition: all 0.3s ease;
}

.indicator.active {
    background: #4A90E2;
    transform: scale(1.2);
}

.indicator:hover {
    background: rgba(74, 144, 226, 0.6);
}

.msg_stats {
    text-align: center;
}

.stats_text {
    font-size: 12px;
    color: rgba(255, 255, 255, 0.7);
    font-weight: 500;
}

/* 加載動畫 */
.loading-spinner {
    display: inline-block;
    width: 16px;
    height: 16px;
    border: 2px solid rgba(255, 255, 255, 0.3);
    border-radius: 50%;
    border-top-color: #fff;
    animation: spin 0.8s linear infinite;
}

@keyframes spin {
    to {
        transform: rotate(360deg);
    }
}

.text-center {
    text-align: center;
}

/* 響應式設計 */
@media (max-width: 480px) {
    .msg_container {
        width: 320px;
        padding: 16px;
        margin: 0 auto; 
    }
    
    .msg_input_area {
        width: 320px;
        max-width: 100%; 
        gap: 10px;
        justify-content: center;
        align-items: center;
    }
    
    .msg_in {
        font-size: 13px;
        flex: 1; 
        min-width: 0; 
    }
    
    .msg_btn {
        font-size: 13px;
        padding: 6px 12px;
        flex-shrink: 0; 
    }
}
</style>