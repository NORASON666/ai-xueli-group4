# 用 AI 讀懂學力檢測

「找出學校的改變方向」：115 學年度第四群組教務主任增能研習的 HTML 簡報 v4。共 51 頁、八段、120 分鐘，附 A1～A3 基本功、P1～P8 分析、D1～D3 桌面版指令、每頁講稿與補充資料。內容依據為「課程規劃 v4.md」；公開版只引用假資料練習素材，真實示範資料只標「示範學校 A／B」與檔案代碼，不收錄原檔、真實校名、人名（周凡淇除外）或實際測驗數據。

## 修改與重建

- `src/content.py`：投影片順序、重點、十四則原文指令與每頁 `notes` 講稿。
- `src/supplements.json`：以頁碼為 key 的補充資料；增刪頁面時一起調整。
- `src/template.html`：共用樣式與操作功能。
- `src/build.py`：把以上內容組裝為 `docs/index.html`，只用 Python 標準函式庫。

在專案實體目錄執行（建議 Python 3.13）：

```sh
python3 src/build.py
python3 -m http.server 8000 --directory docs
```

開啟 <http://localhost:8000>。左右方向鍵換頁，`Q` 研習 LINE 群組 QR、`O` 總覽、`S` 補充、`N` 講稿、`T` 倒數計時、`F` 全螢幕，`Esc` 關閉面板或 QR；指令頁按「複製」。工具列平常淡化縮小，游標移到上方區域或工具列取得焦點時完整顯示。剪貼簿功能請使用 localhost 或 HTTPS。字型使用 Google Fonts，無網路時使用系統替代字型。

插圖放在 `docs/assets/illus/`：`cover_bg`（封面與結語），八段依序為 `sec_open`、`sec_talk`、`sec_basics`、`sec_report`、`sec_cross`、`sec_desktop`、`sec_practice`、`sec_share`。副檔名由建置程式辨識，缺圖時顯示「製作中」；補圖後請重新建置。新增桌面版原圖為 `art/illus/sec_desktop.png`（4:3），公開版 JPG 寬 1200、品質 85。

練習圖放在 `docs/assets/shots/`：`practice_scores.jpg`、`practice_items.jpg`、`practice_whiteboard.jpg`、`practice_postits.jpg`。下載包為 `docs/assets/files/練習素材_假資料4張.zip`。素材由另一程序提供，本專案只引用；`art/` 是產圖工作區，不納入 git。

日後 GitHub Pages 可選擇由 `main` 的 `/docs` 發布。本次沒有建立遠端 repository 或推送。

## 頁碼

封面第 1 頁。開場 2–5（5 分鐘，當天範例資料在第 4 頁）；說一說 6–11（10 分鐘）；AI 基本功 12–21（20 分鐘，含 5 分鐘練習）；現場示範一 22–26（15 分鐘）；現場示範二 27–33（15 分鐘）；桌面版 34–42（20 分鐘）；實作 43–46（25 分鐘）；分享收斂 47–51（10 分鐘，含結語）。每段第一頁都是 divider。

v4 驗收報告：`output/v4-verification.md`（含「頁碼｜頁面標題｜補充標題」完整核對表）；重跑 `python3.13 output/verify_xueli_v4.py`。桌面版安裝與本機專案權限依 OpenAI 官方說明核對；研習前仍須用講師帳號試跑，並準備批次輸出。

示範學校資料不放在網頁上。請勿把班級報表、逐生資料或未公開題本加入專案。
