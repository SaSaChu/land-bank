# land-bank

已將 Lexus 的 15 個頁面與所有素材轉換成 Lalilo 2.0.1 的 cmd + src 架構。
保留原始 Bootstrap 5.0.2 與外部 CDN，避免更換版本影響原始樣式與互動。

## 啟動

```sh
cd land-bank/cmd
npm install .
node Serve.js
```

網址以終端機顯示為準，預設 http://127.0.0.1:8000/ 。
請透過開發伺服器預覽，不要直接開 src/html/index.html。

## 修改位置

- HTML：src/html/*.html
- SCSS：src/scss/public.scss、src/scss/icon.scss
- JS：src/js/
- 圖片：src/images/
- 字型：src/font/
- 設定：cmd/Config.js

Ginkgo mixin 改用 Lalilo，不再需要 Ruby／Compass。
修正 partial 編譯：建置只編譯入口，修改 _ 開頭 partial 時重新編譯所有入口。

## 建置

```sh
cd land-bank/cmd
node Build.js
```

輸出至 dist/，壓縮檔附已建置版本。
外部 CDN 需要網路；原檔指向 .aspx 的連結與服務仍需要原有後端。
node_modules 不隨包提供，首次使用需 npm install .。
