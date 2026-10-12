# 任務：BMI 計算器 v3 — 中英雙語版（English + 繁體中文）

From: 領隊 洄瀾 → 隊員 太魯閣
Date: 2026-10-12
Reference: `workspace/outbox/20261012-bmi-calculator-v2.html`

## 做什麼 / What
以 v2 為基礎做 **v3 雙語版**，另存新檔 `workspace/outbox/20261012-bmi-calculator-v3.html`。
**v1、v2 檔案一律保持原樣，不得修改。**

### 功能要求
1. **語言切換鈕**：頁面右上角放一個切換鈕，例如 `EN | 中`。點擊即切換全站介面語言，預設**繁體中文**。
2. **可切換的文字**（兩語都要完整、自然，不是機翻腔）：
   - 標題、身高/體重標籤與單位（公分/公斤 ↔ cm/kg）、placeholder、按鈕（計算/清除 ↔ Calculate/Reset）
   - 錯誤訊息（空值、非數字、非正數）
   - 結果區文字、六級評語（過輕/體重正常/過重/輕度肥胖/中度肥胖/重度肥胖 ↔ Underweight/Normal/Overweight/Mild obesity/Moderate obesity/Severe obesity）
   - 頁尾警語（英文版：`BMI categories follow Taiwan's Health Promotion Administration adult standards. Not applicable to children or pregnant women.`）
3. **切換時機**：已在畫面上的結果與錯誤訊息也要跟著換語言，不能只切表單。
4. **計算邏輯與 v2 完全一致**：`toFixed(1)` 四捨五入、用進位後的值分級、六級門檻 18.5/24/27/30/35 不變。
5. `<html lang>` 屬性要跟著切換（`zh-TW` ↔ `en`）。
6. 實作方式建議：JS 內建兩組字串對照表（object）切換即可，不引任何外部資源（不能用 CDN 翻譯 API）。

## 格式 / Format
- 單一 HTML 檔，CSS/JS 內嵌，離線可用，瀏覽器雙擊即開。
- 版面延續 v2 卡片風格，只加切換鈕，不要大改版。

## 怎樣算做完 / Done looks like
- 開檔預設繁中，點切換鈕後**所有文字**（含已顯示的結果/錯誤）變英文，再點切回。
- 自測並寫進交接：
  - 中文模式：170/65 → `22.5`「體重正常」
  - 英文模式：170/70 → `24.2`「Overweight」
  - 錯誤訊息兩語都正確顯示
- git：驗收前先做一個 commit（訊息：`feat: add bilingual en/zh-TW BMI calculator v3`）並 push。
- 在 `workspace/outbox/` 留交接檔：做了什麼、哪裡要注意、能不能直接用。

🚫 不刪任何檔案；不改 v1/v2；不引外部資源。
