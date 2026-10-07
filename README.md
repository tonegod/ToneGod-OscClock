# ToneGod-OscClock

瀏覽器版示波器時鐘：用聲卡送出立體聲 X‑Y 訊號（L = X、R = Y），讓實體示波器在 X‑Y 模式畫出時鐘。HTML、CSS 與 JavaScript 內嵌於 `index.html`，無外部套件或建置步驟（Google Fonts 載入失敗時會改用系統字型）。

## 本機使用

```sh
cd /Users/morimagic/Desktop/ToneGod-Player/ToneGod-OscClock/web
python3 -m http.server 8000 --bind 127.0.0.1
```

開啟 http://localhost:8000 ，按 **ARM** 開始送出訊號。AudioWorklet 需要安全來源（HTTPS 或 localhost）；不支援時會改用 ScriptProcessor fallback。

接法：聲卡輸出 → 示波器 CH1 (X) / CH2 (Y)，示波器切 X‑Y、建議 DC 耦合。先調低音量，不要接喇叭或耳機。

## 功能

- 形式：時:分、時:分:秒、指針、指針＋數字；12/24 小時制。
- 字體：LED（老式七段 LED）、DOT 5×7（點陣）、SEG‑7、ITALIC、ROUND、CYBER。
- 整個畫面是一條不中斷的路徑（底線連接各數字、每筆畫來回描），數位示波器不會出現跳線斜線。
- Z‑AXIS / 3D：X/Y/Z 旋轉、自動旋轉、透視、厚度（立體字）。旋轉在音訊執行緒逐取樣計算。
- 輸出裝置與路由：「⟳ 掃描」列出聲卡（Chrome/Edge 需麥克風授權才顯示名稱，不會錄音），X/Y 可指定任一輸出通道。
- 設定存在目前瀏覽器（localStorage key `oscchrono`）。快捷鍵：H 迷你模式、F 全螢幕、空白鍵 ARM。

## Git 範圍

本目錄作為獨立網頁倉庫；不包含原生 app 的 Source、CMake、build、dist 或 ToneGod-Player 其他工程。原生 app 在上一層 `ToneGod-OscClock/`。

## 驗證限制

可用 Node 的 `--check` 檢查內嵌 JavaScript。無既有 lint/test/build 指令；語法檢查不代表聲卡輸出、示波器顯示或瀏覽器權限測試通過。
