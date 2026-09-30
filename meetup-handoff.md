# meetup 交接

## 專案狀態

- 2026-10-01 已發布至 GitHub master，GitHub Pages 建置與公開頁面驗證成功；本機分支 `codex/update-kktix-events`。查法：`git status -sb`、`git log -1 --oneline`、`git diff --stat origin/master...HEAD`。
- README 整理 45 場 KKTIX 公開活動（41 場有編號聚會、4 場 COSCUP 前哨戰），另保留 4 場舊索引紀錄。最新公開紀錄為 2021-10-12 第 46 場，無近期公開活動；查 [KKTIX](https://skymizer.kktix.cc/)。
- GitHub Pages 來源是 `master` 根目錄，首頁已顯示活動索引。查法：`gh api repos/CatSystemWorkshop/meetup/pages --jq '{html_url,source,status}'`、`curl -fsSL https://catsystemworkshop.github.io/meetup/`。
- 已逐場比對 JSON-LD 的開始日期與主題、驗證 49 列資料及既有筆記／PDF 連結；本機 Jekyll 成功展開首頁 include 並轉成 6 個 HTML 表格。
- 本機沒有 `jekyll-theme-leap-day` 套件；內容建置驗證使用任務暫存設定停用 theme，未安裝套件。發布後已確認遠端建置成功、公開頁面含 6 個表格／49 列活動，瀏覽器中完整主題樣式正常。

## 決策記錄

- 保留既有筆記與投影片原文，索引日期採 KKTIX。第 20 場 KKTIX 為 2017-10-17，舊筆記為 2017-10-03，README 已註明差異。
- 第 8–11 場來自舊 README，KKTIX 公開列表沒有對應頁面；保留原紀錄而不猜連結。第 12 場無來源，不補造紀錄。
- `index.html` 使用 `include_relative README.md` 與 `markdownify`，只維護一份活動內容。保留原 leap-day 主題。
- PLAN 與本交接文件由專案 repo 追蹤，文字限專案資訊，並從 Jekyll 發布內容排除；快取與建置產物由 `.gitignore` 排除。

## 下一步

- 本次更新已完成，無主動待辦。未來新增活動時更新 README，首頁會同步呈現。
- 建置查法：`gh api repos/CatSystemWorkshop/meetup/pages/builds/latest --jq '{status,error,commit}'`；公開頁：<https://catsystemworkshop.github.io/meetup/>。
