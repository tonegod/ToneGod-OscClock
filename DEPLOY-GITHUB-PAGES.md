# ToneGod-OscClock GitHub Pages

- 預定倉庫：https://github.com/tonegod/ToneGod-OscClock （尚未建立；建立與公開前需使用者確認）。
- 預定網頁：https://tonegod.github.io/ToneGod-OscClock/
- 部署來源：`main` 分支根目錄，入口為 `index.html`。
- 本機：`ToneGod-Player/ToneGod-OscClock/web`，獨立 Git 倉庫。
- 網頁倉庫只包含 HTML、README、部署說明及 .gitignore，不包含原生工程或其 build/dist。

首次發佈：

```sh
cd /Users/morimagic/Desktop/ToneGod-Player/ToneGod-OscClock/web
git remote add origin https://github.com/tonegod/ToneGod-OscClock.git
git push -u origin main
```

再到 GitHub 倉庫 Settings → Pages → Source 選 `main` / root。之後每次提交並推送 `main`，Pages 會重新部署。
