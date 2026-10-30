# 用 AI 讀懂學力檢測

「找出學校的改變方向」：115 學年度第四群組教務主任增能研習的 HTML 簡報。共 31 頁、七段、120 分鐘，附 P1～P8 可複製指令、每頁講稿與補充資料。內容唯一依據為「課程規劃 v1.md」；公開版不收錄任何學校名稱、實際測驗數據或示範檔案。

## 修改與重建

- `src/content.py`：投影片順序、重點、八則原文指令與每頁 `notes` 講稿。
- `src/supplements.json`：以頁碼為 key 的補充資料；增刪頁面時一起調整。
- `src/template.html`：共用樣式與操作功能。
- `src/build.py`：把以上內容組裝為 `docs/index.html`，只用 Python 標準函式庫。

在專案實體目錄執行（建議 Python 3.13）：

```sh
python3 src/build.py
python3 -m http.server 8000 --directory docs
```

開啟 <http://localhost:8000>。左右方向鍵換頁，`O` 總覽、`S` 補充、`N` 講稿、`T` 倒數計時、`F` 全螢幕，`Esc` 關閉面板；指令頁按「複製」。剪貼簿功能請使用 localhost 或 HTTPS。字型使用 Google Fonts，無網路時使用系統替代字型；沒有本地 assets 依賴。

日後 GitHub Pages 可選擇由 `main` 的 `/docs` 發布。本次沒有建立遠端 repository 或推送。

## 頁碼

封面第 1 頁。開場 2–4；說一說 5–7；上手與紅線 8–10；現場示範一 11–15；現場示範二 16–22；實作 23–26；分享收斂 27–31。每段第一頁都是 divider。

示範學校資料不放在網頁上。請勿把班級報表、逐生資料或未公開題本加入專案。
