# 交接：已完成 BMI 計算器 v3 中英雙語版；右上角配置流暢語言切換鈕，支援即時文字、錯誤訊息與結果評語全動態雙向切換；完成自測與 git commit/push；可直接於瀏覽器開啟使用。

From: 隊員 太魯閣 → 領隊 洄瀾
Date: 2026-10-12
Task Reference: `workspace/inbox/20261012-bmi-calculator-v3-bilingual.md`
Finished Product: `workspace/outbox/20261012-bmi-calculator-v3.html`
Previous Products: `20261012-bmi-calculator.html` (v1), `20261012-bmi-calculator-v2.html` (v2) 均保持原樣，未作任何修改。

## 完成項目檢核 / Checklist

1. **雙語切換按鈕**：
   - 位於卡片標題右側（`中文` / `EN` 膠囊式切換鈕），預設為繁體中文 (`zh-TW`)。
   - 點擊即切換全站語言，同步切換 `<html lang>` 屬性（`zh-TW` ↔ `en`）及 `<title>`。
2. **文字對照與本地化**：
   - 表單標籤、單位（公分/公斤 ↔ cm/kg）、placeholder、按鈕（計算/清除 ↔ Calculate/Reset）。
   - 錯誤訊息：空值、非數字、非正數均提供自然中英文提示。
   - 國健署成人六級評語完整對照：
     - 過輕 ↔ Underweight
     - 體重正常 ↔ Normal
     - 過重 ↔ Overweight
     - 輕度肥胖 ↔ Mild obesity
     - 中度肥胖 ↔ Moderate obesity
     - 重度肥胖 ↔ Severe obesity
   - 頁尾警語英文完全相符：`BMI categories follow Taiwan's Health Promotion Administration adult standards. Not applicable to children or pregnant women.`
3. **即時動態連動**：
   - 已呈現在畫面上的運算結果或錯誤警語，在切換語言時會立即同步轉換，使用者體驗流暢。
4. **計算邏輯**：
   - 完全延續 v2 規格：`rawBmi.toFixed(1)` 標準四捨五入，並以進位後數值判定六級標準。
5. **獨立性**：
   - 單一 HTML 檔案，不使用任何外部 CDN 或翻譯 API，完全支援離線使用。

## 自測結果 / Self-test Results
- **測試 1（繁中模式）**：
  - 輸入 170cm / 65kg → 顯示 `22.5`，評語為 `體重正常`。
- **測試 2（英文模式）**：
  - 輸入 170cm / 70kg → 顯示 `24.2`，評語為 `Overweight`。
- **測試 3（動態語言切換）**：
  - 在中文計算出結果後點擊「EN」，評語立即轉為英文，數值保持 `22.5`；再點「中文」即刻切回。
  - 在出現錯誤提示狀態下切換語言，錯誤文字亦即時轉換。
- **測試 4（錯誤防呆）**：
  - 中文：「請完整輸入身高與體重數值。」／「輸入格式不正確，請輸入數字。」／「身高與體重必須為大於 0 的正數。」
  - 英文："Please enter both height and weight." / "Invalid format. Please enter numbers only." / "Height and weight must be positive numbers greater than 0."
