# Eloquent Reflection — 沉浸式心靈復盤 App

## 專案概述
幫助現代人把「寫日記/自我反省」變成像玩遊戲一樣有視覺療癒感的前端網頁作品。

## 核心痛點
高壓生活下的人知道「復盤」能緩解焦慮，但傳統日記太無聊，容易放棄。

## 三大功能模組

### 1. 格子牆（Contribution Graph）
- 仿 GitHub 貢獻圖，週/月格子牆
- 每天完成復盤就亮起一格
- 強化連續記錄（Streak）成就感

### 2. 沉浸式 3 步驟表單
- **能量滑桿**：拖動記錄今日精神飽滿度（1–10）
- **今日最大勝利**：一兩句寫下今天最值得肯定的事
- **心情標籤**：點選當下情緒（平靜 / 焦慮 / 充實 / 感恩 / 疲憊）

### 3. 精靈/像素植物（情緒伴生）
- 根據心情動態生長的像素寶石或電子植物
- 低落焦慮 → 藍色水晶蓄能
- 能量爆棚 → 黃金植物生長動畫

## 視覺風格
- **主色調**：暗黑 Cyberpunk（深色背景 #0D0D1A）
- **輔助風格**：微新擬態（Neumorphism）
- **字型**：現代等寬 + 無襯線搭配
- **強調色**：紫 / 青 / 金漸層

## 技術棧
- 純 HTML + CSS + JavaScript（無框架）
- 單一 index.html 入口

## 設計系統（Design System）

### 互動元件規範

#### 輸入框 Focus 狀態 — 極光邊框
```css
/* 預設：無邊框，Neumorphism 內凹陰影 */
border: 1px solid transparent;
box-shadow: inset 4px 4px 8px var(--shadow-dark),
            inset -2px -2px 6px var(--shadow-light);
transition: box-shadow 0.4s ease, border-color 0.4s ease;

/* Focus 啟動：青藍色三層極光 */
border-color: var(--cyan);          /* 實線邊框 */
box-shadow:
  inset 4px 4px 8px var(--shadow-dark),
  inset -2px -2px 6px var(--shadow-light),
  0 0 0 2px var(--cyan-glow),       /* 第一層：緊貼邊框光暈 */
  0 0 12px var(--cyan-glow),        /* 第二層：中距離散射 */
  0 0 24px rgba(6,182,212,0.15);    /* 第三層：遠距離大氣光 */
```
- 顏色：`var(--cyan)` = 深色 `#06B6D4` / 淺色 `#0891B2`
- 過渡時間：`0.4s ease`
- 適用元件：所有文字輸入框（textarea、input[type=text]）

---

## 語言偏好
- 繁體中文回覆
- 禁止第一/第二人稱代名詞（摘要任務）
