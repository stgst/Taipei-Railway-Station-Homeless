<script setup>
import { ref, onMounted, onUnmounted } from 'vue'
import Btn from '@/components/Btn.vue'

// 響應式數據
const currentIndex = ref(0)
let intervalId = null

// API URL
const API_URL = 'https://script.google.com/macros/s/AKfycbypXWYPXt1NFYcwxf4FCnxbqcAF4_XzvowBiUC4ysndMzMNRyMH_HOKza7GYpjLUVn1/exec'

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
                body: JSON.stringify({ "comment": newMessage.value.trim() })
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
        <div
            class="container mx-auto px-4 py-8 md:mt-auto w-xs md:w-md text-left text-lg max-h-screen overflow-y-auto space-y-6">
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
                        <img src="../assets/img/大廳一.jpg" alt="圖片1"
                            class="w-full h-auto rounded-lg shadow-md object-cover max-w-xs" />
                        <img src="../assets/img/大廳二.JPG" alt="圖片2"
                            class="w-full h-auto rounded-lg shadow-md object-cover max-w-xs" />
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
                        <img src="../assets/img/傳統民謠.jpg" alt="圖片1"
                            class="w-full h-auto rounded-lg shadow-md object-cover max-w-xs" />
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
            </div>
            <div class="msg_container">
                <div class="msg_input_area">
                    <input v-model="newMessage" type="text" class="msg_in" placeholder="分享你的想法..."
                        @keyup.enter="addMessage" :disabled="isSubmitting">
                    <button @click="addMessage" class="msg_btn" :disabled="!newMessage.trim() || isSubmitting">
                        <span v-if="isSubmitting" class="loading-spinner"></span>
                        <span v-else>💬 留言</span>
                    </button>
                </div>

                <div class="msg_card_display" @mouseenter="stopCarousel" @mouseleave="startCarousel">
                    <div v-if="messages.length === 0" class="msg_card active">
                        <div class="msg_content text-center">
                            <div class="msg_text">暫無留言，來分享你的想法吧！</div>
                        </div>
                    </div>
                    <div v-else v-for="(message, index) in messages" :key="message.id"
                        :class="['msg_card', { active: index === currentIndex }]">
                        <img src="../assets/img/user.png" class="avatar">
                        <div class="msg_content">
                            <div class="msg_name">{{ message.name }}</div>
                            <div class="msg_text">{{ message.text }}</div>
                        </div>
                    </div>
                </div>

                <!-- 指示器 -->
                <div class="msg_indicators">
                    <button v-for="(message, index) in messages" :key="`indicator-${message.id}`"
                        @click="goToMessage(index)" :class="['indicator', { active: index === currentIndex }]"></button>
                </div>
                <!-- 留言統計 -->
                <div class="msg_stats">
                    <span class="stats_text">共 {{ messages.length }} 則留言</span>
                </div>
            </div>
            <div class="flex justify-center">
                <div class="grid grid-cols-1 sm:grid-cols-2 gap-4">
                    <img src="../assets/img/往東森街上的閒聊一.jpg" alt="圖片1"
                        class="w-full h-auto rounded-lg shadow-md object-cover max-w-xs" />
                    <img src="../assets/img/往東森街上的閒聊二.jpg" alt="圖片1"
                        class="w-full h-auto rounded-lg shadow-md object-cover max-w-xs" />
                </div>
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