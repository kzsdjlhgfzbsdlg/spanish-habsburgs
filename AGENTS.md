# AGENTS.md - 西班牙哈布斯堡王朝沉浸式歷史講義規範

## 1. 專案核心定位
- **目標**：專注於「歷史氛圍與沉浸式閱讀」的數位講義網站，**嚴禁加入任何測驗、評量或考試機制**。
- **架構原則**：資料（JSON）與視圖（HTML/CSS/JS）嚴格分離，確保未來可透過修改或新增 JSON 快速擴充內容。
- **視覺風格**：西班牙黃金世紀（Siglo de Oro）古典風。主色調為深緋紅（`#7A1C1C`）、皇室金（`#C59B27`）、羊皮紙米色（`#FAF6F0`），搭配襯線字體（Noto Serif TC）。

## 2. 頁面結構與互動規範
- **中心時間線（Central Timeline）**：
  - 頁面正中央必須有一條貫穿整頁的垂直金色時間軸。
  - 歷史事件卡片與圖片卡片採用「左右交錯（Zigzag）」方式排列於時間軸兩側。
  - 支援滾動漸顯（Scroll Reveal）動畫，隨著讀者向下滑動，歷史事件會依序優雅浮現。

## 3. 圖片與歷史考據規範
- **AI 自動配圖原則**：每個歷史事件的 `imageUrl` 必須對應歷史上真實存在的藝術品（如委拉斯蓋茲、提香的油畫）或真實古蹟照片，優先使用 Wikimedia Commons 的公有領域（Public Domain）直鏈，並附上 `imageCaption` 說明出處。

## 4. 資料格式 Schema (`data/chXX-[slug].json`)
當使用者要求「新增歷史事件」或「擴充新章節」時，AI 必須嚴格遵守以下 JSON 結構，不可隨意更改鍵名：
```json
{
  "id": "ch01",
  "chapterNumber": "全景歷史時間軸",
  "title": "主標題",
  "period": "西元年份區間",
  "description": "章節核心導讀",
  "timelineEvents": [
    {
      "year": "年份（如：1516 年）",
      "title": "事件標題",
      "content": "歷史經過與文化影響說明",
      "imageUrl": "[https://upload.wikimedia.org/](https://upload.wikimedia.org/)...",
      "imageCaption": "畫作名稱與典藏美術館說明"
    }
  ]
}