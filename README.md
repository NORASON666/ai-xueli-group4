# 用 AI 讀懂學力檢測

「找出學校的改變方向」：115 學年度第四群組教務主任增能研習的 HTML 簡報 v2。共 39 頁、七段、120 分鐘，附 A1～A3 基本功與 P1～P8 分析指令、每頁講稿與補充資料。內容依據為「課程規劃 v2.md」；公開版只引用假資料練習素材，不收錄真實校名、人名（講師除外）或實際測驗數據。

## 修改與重建

- `src/content.py`：投影片順序、重點、十一則原文指令與每頁 `notes` 講稿。
- `src/supplements.json`：以頁碼為 key 的補充資料；增刪頁面時一起調整。
- `src/template.html`：共用樣式與操作功能。
- `src/build.py`：把以上內容組裝為 `docs/index.html`，只用 Python 標準函式庫。

在專案實體目錄執行（建議 Python 3.13）：

```sh
python3 src/build.py
python3 -m http.server 8000 --directory docs
```

開啟 <http://localhost:8000>。左右方向鍵換頁，`O` 總覽、`S` 補充、`N` 講稿、`T` 倒數計時、`F` 全螢幕，`Esc` 關閉面板；指令頁按「複製」。工具列平常淡化縮小，游標移到上方區域或工具列取得焦點時完整顯示。剪貼簿功能請使用 localhost 或 HTTPS。字型使用 Google Fonts，無網路時使用系統替代字型。

插圖放在 `docs/assets/illus/`：`cover_bg`（封面與結語），七段依序為 `sec_open`、`sec_talk`、`sec_basics`、`sec_report`、`sec_cross`、`sec_practice`、`sec_share`。副檔名由建置程式辨識，缺圖時顯示「製作中」；補圖後請重新建置。

練習圖放在 `docs/assets/shots/`：`practice_scores.jpg`、`practice_items.jpg`、`practice_whiteboard.jpg`、`practice_postits.jpg`。下載包為 `docs/assets/files/練習素材_假資料4張.zip`。素材由另一程序提供，本專案只引用；`art/` 是產圖工作區，不納入 git。

日後 GitHub Pages 可選擇由 `main` 的 `/docs` 發布。本次沒有建立遠端 repository 或推送。

## 頁碼

封面第 1 頁。開場 2–4（10 分鐘）；說一說 5–8（15 分鐘）；AI 基本功 9–18（20 分鐘，含 5 分鐘練習）；現場示範一 19–23（20 分鐘）；現場示範二 24–30（20 分鐘）；實作 31–34（25 分鐘）；分享收斂 35–39（10 分鐘，含結語）。每段第一頁都是 divider。

示範學校資料不放在網頁上。請勿把班級報表、逐生資料或未公開題本加入專案。
