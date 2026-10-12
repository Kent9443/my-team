# my-team 專案

本專案為 AI 雙人協作（領隊 Wailan 洄瀾 ＋ 隊員 Taroko 太魯閣）與人類小隊長（Captain）配對協同的實作專案。

## 資料夾結構 / Workspace Structure

專案依據團隊公約分為三個格子進行協作：

```
workspace/
├── inbox/    📥 領隊放置任務紙條（Task notes）
├── outbox/   📤 隊員放置完成的成品與交接檔（Deliverables & handoffs）
└── shared/   📚 團隊共用的原始資料與活動範例（唯讀，不寫入）
```

## BMI 計算器 / BMI Calculator

本專案於 `workspace/outbox/` 內包含符合衛生福利部國民健康署成人標準的單一檔案 BMI 計算器：
- **當前有效版本（v2）**：[`workspace/outbox/20261012-bmi-calculator-v2.html`](workspace/outbox/20261012-bmi-calculator-v2.html)
- **初始版本（v1）**：[`workspace/outbox/20261012-bmi-calculator.html`](workspace/outbox/20261012-bmi-calculator.html)

### 如何開啟使用
直接雙擊上述 `.html` 檔案或拖曳至任何現代瀏覽器（Chrome、Edge 等）即可離線開啟使用。輸入身高（公分）與體重（公斤）後點擊「計算」即可取得 BMI 數值與六級成人體重判定評語。

## 版本控制規則 / Version Control Rules

1. **Commit 紀律**：每次成品或修改驗收通過後進行一次 commit，訊息以英文小寫開頭並簡述變更內容（例如：`init: team workspace with BMI calculator v1 & v2`）。
2. **改版不刪舊檔**：版本更新時採用另存新檔（如 `-v2`），不覆寫第一版，確保歷史紀錄完整可追溯。
3. **個資安全檢查**：專案設定為公開 Repository，嚴禁提交任何個人資料（姓名、學號、照片、電話、Email 等）；每次 push 前必須再次執行個資掃描。
