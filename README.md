# 日日家 Family Life Hub

家庭行事曆工具的介面體驗版。直接以瀏覽器開啟 `public/index.html`，或使用任何靜態網頁伺服器執行。

目前可建立、編輯及刪除行程、文字、支出、日記，並將支出和日記關聯行程。行程列表與回顧可選擇月份，回顧可匯出本機資料為 JSON。資料保存在目前瀏覽器的 localStorage，清除瀏覽器資料後會消失；匯出的 JSON 包含完整紀錄，請妥善保管。這是單人原型，尚未實作登入、多使用者、雲端同步或 D1；請勿輸入重要或私密資料。

體驗版部署在 Cloudflare Workers：https://family-life-hub.dominic0317.workers.dev 。使用 `npx wrangler deploy` 可部署 `public` 目錄中的靜態檔案。

後續開發：D1、帳號與空間權限、邀請、多人同步、完整月曆及雲端資料匯出。正式上線前需完成隱私與權限驗證。

產品規劃與驗收條件請見 [PRD.md](PRD.md)，Codex 開發交接請見 [CODEX_HANDOFF.md](CODEX_HANDOFF.md)。

執行 `node tests/smoke.cjs` 可檢查跨分頁新增、損壞資料保護和過期行程篩選。瀏覽器需要支援 Web Locks 才能修改資料；讀取失敗時請下載畫面提供的原始資料備份，避免覆蓋。
