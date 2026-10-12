# 任務：為這個資料夾建立 Git + GitHub 版本控制（GitHub CLI）

From: 領隊 洄瀾 → 隊員 太魯閣
Date: 2026-10-12
Captain's decisions: 安裝 Git 與 GitHub CLI；Repo 名稱 **my-team**；**Public**。

## 前置條件 / Setup (member does this)
1. 安裝（小隊長已批准）：
   - `winget install --id Git.Git -e --source winget`
   - `winget install --id GitHub.cli -e --source winget`
2. 安裝後若指令找不到，先告知小隊長需重開終端機，等確認後再繼續，不要硬做。
3. `gh auth login`（瀏覽器授權）— 若需要小隊長掃 QR code 或按確認，停下來請小隊長處理。

## 做什麼 / What
在 `C:\Users\NDHU CSIE\Documents\my-team` 內：

1. **先掃描個資（強制）**：public repo = 全世界可見。檢查所有檔案內容是否含姓名、學號、照片、email 等個資。發現任何個資 → **停下來回報小隊長**，不要提交、不要 push。
2. `git init`（若尚未是 repo）。
3. 建立 `.gitignore`，至少包含：
   ```
   # 個資與系統檔
   *.png
   *.jpg
   *.jpeg
   *.gif
   .DS_Store
   Thumbs.db
   desktop.ini
   ```
4. 建立 `README.md`（放在資料夾根目錄；若已存在就更新）：簡單說明這是什麼、`workspace/` 三個格子的結構、如何開啟 BMI 計算器。
5. 第一次 commit（訊息：`init: team workspace with BMI calculator v1 & v2`）。
6. 用 GitHub CLI 建立 public repo 並推送：
   ```
   gh repo create my-team --public --source=. --remote=origin --push
   ```
7. 之後的 commit 紀律（寫進 README 的「版本控制規則」小節）：
   - 每次成品/修改驗收後一個 commit，訊息英文小寫开头、簡述做了什麼。
   - 版本改版（-v2）不刪舊檔，一起 commit，保留歷史。
   - 不要 commit 個資檔；push 前再掃一次。

## 格式 / Format
- 以上皆在本資料夾內執行；不得 push 到其他 repo、不得建立其他分支以外的東西（main 即可）。
- 不刪任何既有檔案。

## 怎樣算做完 / Done looks like
- `git log` 顯示至少一個 commit。
- `gh repo view` 顯示 `my-team` public repo 已存在且已推送。
- 個資掃描結果寫在交接裡（掃了哪些檔案、結論）。
- 在 `workspace/outbox/` 留交接檔：做了什麼、repo URL、哪裡要注意、能不能直接用。
