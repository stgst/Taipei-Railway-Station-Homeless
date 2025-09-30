# 台北車站無家者議題線上展覽 🏠

> 「冬天的夜晚，姐姐會摘下弦月，輕輕刮除整座城市寂寞的細節。」—— 周盈秀《我姐姐住台北》

一個以理解與同理為出發點的無家者議題互動式線上展覽，帶您走進台北車站周邊無家者的真實生活世界。

## 📖 項目簡介

本項目是與無家者議題倡議組織「人生百味」合作開發的線上互動展覽。透過無家者 OA 大哥的親身分享，以 90 分鐘的虛擬導覽形式，帶領觀眾認識台北車站周邊無家者的生活現況、挑戰與故事。

我們希望這不僅是一場展覽，更是一段理解與行動的開始，讓更多人以平等的心態與同理的角度去理解無家者議題。

## 🎯 展覽目標

- **破除刻板印象**：超越「同情」的表面情感，建立平等的理解關係
- **真實呈現**：透過無家者第一人稱視角，呈現真實的生活經驗
- **促進對話**：提供互動留言功能，鼓勵觀眾反思與討論
- **社會教育**：提升大眾對無家者議題的認識與關注

## 🏛️ 展覽路線

### 📍 導覽地點
1. **台北車站 東三門** - 展覽開場與議題介紹
2. **台北車站周圍** - 無家者生活區域巡禮
3. **台北車站 南一門內** - 工作與薪水現況
4. **台北車站 大廳** - 日常生活體驗
5. **東森地下街** - 深度問答與政策討論

### 🎬 展覽內容
- **真實故事分享**：OA 大哥的無家者生活經驗
- **空間介紹**：台北車站各門區的功能與特色
- **議題探討**：無家者面臨的實際困境與需求
- **互動問答**：觀眾可即時留言參與討論
- **政策反思**：政府援助制度的現況與限制

## 💻 技術規格

### 🛠️ 使用技術
- **前端框架**：Vue 3 (Composition API)
- **構建工具**：Vite
- **樣式框架**：Tailwind CSS 4.x
- **動畫庫**：Animate.css
- **HTTP 客戶端**：Axios
- **部署平台**：GitHub Pages

### 🏗️ 項目結構
```
homeless_front/
├── public/                     # 靜態資源
├── src/
│   ├── assets/                # 資源文件
│   │   ├── img/              # 圖片資源
│   │   └── stylesheet.css    # 全域樣式
│   ├── components/           # Vue 組件
│   │   ├── Home.vue         # 首頁
│   │   ├── Intro.vue        # 介紹頁
│   │   ├── first.vue        # 展覽第一站
│   │   ├── first2.vue       # 展覽第一站延續
│   │   ├── sec.vue          # 展覽第二站
│   │   ├── third.vue        # 展覽第三站
│   │   ├── fourth.vue       # 展覽第四站
│   │   ├── fifth.vue        # 展覽第五站
│   │   ├── end.vue          # 結尾頁
│   │   ├── thank_page.vue   # 感謝頁
│   │   └── Btn.vue          # 導航按鈕
│   ├── App.vue              # 主應用組件
│   └── main.js             # 應用入口
├── index.html              # HTML 模板
├── package.json            # 項目配置
├── vite.config.js         # Vite 配置
└── jsconfig.json          # JavaScript 配置
```

## 🚀 快速開始

### 📋 環境要求
- Node.js 16.0+
- npm 或 yarn 或 pnpm

### 🔧 安裝步驟
1. **克隆項目**
```bash
git clone https://github.com/stgst/Taipei-Railway-Station-Homeless.git
cd homeless_front
```

2. **安裝依賴**
```bash
npm install
# 或
yarn install
# 或
pnpm install
```

3. **啟動開發服務器**
```bash
npm run dev
# 或
yarn dev
# 或
pnpm dev
```

4. **構建生產版本**
```bash
npm run build
# 或
yarn build
# 或
pnpm build
```

5. **部署到 GitHub Pages**
```bash
npm run deploy
# 或
yarn deploy
# 或
pnpm deploy
```

## 🔗 相關連結

- **線上展覽**：[展覽網址](https://stgst.github.io/Taipei-Railway-Station-Homeless/)
- **GitHub Repo**：[項目代碼](https://github.com/stgst/Taipei-Railway-Station-Homeless)
- **人生百味官網**：[了解更多無家者議題](https://doyouaflavor.tw/)