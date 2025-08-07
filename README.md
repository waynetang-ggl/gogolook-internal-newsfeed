# Gogolook Internal AI Newsletter Landing Page

這是一個為 Gogolook 內部 AI 電子報設計的訂閱 Landing Page。

## 專案背景

Gogolook Internal AI Newsfeed 的概念起源於 DayONE 團隊的內部需求。前幾個月團隊密切的協助 Whoscall 進行和 World ID 的合作研究，於是用自動化流程每天撈取 World ID, Worldcoin, World App 的相關新聞，來跟上 web3 公司的最新消息。

後來團隊觀察後發現，各團隊每個階段都會有較密切關注的議題需要追蹤，但較難主動更新資訊，於是團隊就實踐了 "pretotype" 的精神，簡單用 vibe coding + LLM 做一個內部的 AI Newsletter，嘗試解決並驗證公司同仁是否也同樣具有需求，也歡迎大家的 Feedback!

## 功能特色

- ✅ **Email 驗證**：只允許 @gogolook.com 結尾的電子郵件地址
- 🏷️ **關鍵字標籤**：用戶可以輸入關鍵字，以標籤形式呈現
- 📡 **RSS 推薦**：支援多個 RSS feed URL 輸入，附帶說明提示
- 📊 **資訊展示**：顯示目前版本的關鍵字和資訊來源
- 💬 **Slack 整合**：提供 Slack 頻道連結
- 🎨 **響應式設計**：適配各種螢幕尺寸
- 🚀 **Webhook 整合**：透過 JSON 格式將資料傳送到 Make

## 資料格式

提交的資料將以 JSON 格式傳送：
```json
{
  "subscriberEmail": "user@gogolook.com",
  "keywordSuggestion": "AI, Machine Learning, Tech News",
  "resourceSuggestion": "https://example.com/rss, https://another.com/feed"
}
```

## 部署到 Vercel

1. 確保您已安裝 Vercel CLI：
   ```bash
   npm i -g vercel
   ```

2. 在專案目錄中執行：
   ```bash
   vercel
   ```

3. 按照提示完成部署設定

## 設定 Webhook

在部署完成後，請：

1. 在 `index.html` 中找到這一行：
   ```javascript
   const webhookUrl = 'YOUR_MAKE_WEBHOOK_URL_HERE';
   ```

2. 將 `YOUR_MAKE_WEBHOOK_URL_HERE` 替換為您的 Make webhook URL

## 本地開發

```bash
# 安裝 Vercel CLI
npm i -g vercel

# 啟動本地開發伺服器
vercel dev
```

## 檔案結構

```
├── index.html          # 主要 HTML 檔案（包含完整功能和樣式）
├── rss-sources.json    # RSS 新聞來源資料
├── keywords.json       # 關鍵字資料
├── vercel.json         # Vercel 部署配置
├── package.json        # 專案配置
├── .gitignore          # Git 忽略檔案
└── README.md          # 說明文件
```

## 頁面內容

1. **訂閱表單區域**
   - Email 驗證（@gogolook.com）
   - 關鍵字許願池（標籤輸入）
   - RSS 資源推薦（多個 URL 輸入）

2. **專案說明區域**
   - README 內容展示
   - 專案背景和理念說明

3. **資訊展示區域**
   - 目前版本關鍵字（前 50 個）
   - 目前版本資訊來源（前 15 個）

4. **Slack 整合**
   - AI NewsFeed in Slack 按鈕

## 注意事項

- 記得在部署後設定正確的 Slack 頻道 URL
- 確認 Make webhook URL 設定正確
- 關鍵字和 RSS 來源資料已內嵌在 HTML 中，便於維護