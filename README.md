# 🏥 CareNotes Generator - DI 藥師衛教單張生成器 (v6.3)

這是一個專為醫院藥物諮詢（DI）藥師設計的輕量級網頁工具。利用 Google Gemini AI 的強大語言能力，協助藥師快速將原始文獻（如 UpToDate, Micromedex PDF 或文字）轉換為符合醫院標準排版格式的「病患衛教單張」。

> **v6.3 版本特色**：針對排版邏輯進行了嚴格分流——副作用項目強制使用橫線（-）條列，注意事項與交互作用則使用數字編號（1) 2) 3)），以符合臨床閱讀習慣。

## ✨ 主要功能

* **📄 PDF 智慧解析**：內建 `PDF.js`，可直接上傳原廠仿單或資料庫 PDF，自動提取文字內容。
* **🤖 AI 驅動生成**：串接 Google Gemini API (支援 1.5 Flash/Pro)，精準翻譯並摘要專業醫學術語。
* **🎨 完美排版 (v6.3)**：
    * **副作用**：自動格式化為橫線條列（避免病患誤解為發生順序）。
    * **禁忌/交互作用**：自動格式化為數字編號 1) 2) 3)。
    * **廢棄物處理**：依據「一般藥品」或「特殊藥品」自動生成對應的廢棄回收警語。
* **🔒 隱私安全**：純前端運作（Client-side Only），API Key 僅儲存於瀏覽器 LocalStorage，不會上傳至任何第三方伺服器。
* **⚡ 即開即用**：無需安裝 Node.js 或 Python，單一 HTML 檔案即可執行。

## 🚀 快速開始

### 1. 取得工具
下載本專案中的 `index.html` 檔案。

### 2. 申請 API Key
本工具需要 Google Gemini API Key 才能運作。
* 前往 [Google AI Studio](https://aistudio.google.com/app/apikey) 免費申請。

### 3. 執行
1.  雙擊 `index.html` 以瀏覽器（建議使用 Chrome 或 Edge）開啟。
2.  在介面上方貼上您的 API Key（系統會自動記憶）。
3.  點擊「🔍 偵測可用模型」確認連線。

### 4. 生成衛教單
1.  輸入 **學名** 與 **商品名**。
2.  選擇 **藥品廢棄類別**（一般藥品/特殊藥品）。
3.  **上傳 PDF** 或直接貼上文獻內容。
4.  點擊「**開始生成衛教單張 🚀**」。

## 🛠️ 技術架構

* **核心語言**：HTML5, JavaScript (ES6+)
* **樣式框架**：[Tailwind CSS](https://tailwindcss.com/) (透過 CDN 引入)
* **PDF 處理**：[PDF.js](https://mozilla.github.io/pdf.js/) (透過 CDN 引入)
* **AI 模型**：Google Gemini API (`gemini-1.5-flash` / `gemini-1.5-pro`)

## 📝 版本更新紀錄

### v6.3 (Current)
* **排版邏輯優化**：透過 Prompt Engineering 強制分離列表格式。
    * *副作用* -> 使用 ` - ` 符號。
    * *注意事項* -> 使用 `1) 2) 3)` 符號。
* **廢棄物邏輯**：修正一般藥品與特殊藥品（抗腫瘤/抗生素/荷爾蒙/管制藥）的回收指導語句。
* **UI 改進**：新增一鍵複製按鈕、載入動畫與狀態提示。

## ⚠️ 注意事項與免責聲明

1.  **AI 幻覺風險**：雖然 Prompt 已針對正確性做過優化，但 AI 仍可能產生錯誤資訊。**藥師務必在發放前進行最終審核與校對。**
2.  **API 使用量**：使用個人的免費版 API Key 有速率限制（Rate Limits），若遇錯誤請稍待幾秒後重試。
3.  **瀏覽器相容性**：建議使用最新版 Chrome、Edge 或 Firefox 以確保 PDF.js 與 Fetch API 運作正常。

## 👤 作者

* **GitHub**: [Almightyhao](https://github.com/Almightyhao)
* **Repository**: [CareNotes-Generator](https://github.com/Almightyhao/CareNotes-Generator)

---
*Created with ❤️ for Pharmacists.*
