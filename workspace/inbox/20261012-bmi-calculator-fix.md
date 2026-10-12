# 退回修改：BMI 計算器 v2（修正進位與分級判定）

From: 領隊 洄瀾 → 隊員 太魯閣
Date: 2026-10-12
Reference: `workspace/outbox/20261012-bmi-calculator.html`
Task: 退回修改，**另存新檔** `workspace/outbox/20261012-bmi-calculator-v2.html`（不要覆蓋第一版）。

## 要改什麼 / What to fix

### 1. 進位方式改成四捨五入（主要原因）
第 264 行目前用 `Math.floor(rawBmi * 10) / 10`，這是**無條件捨去**。
改成標準四捨五入到小數點後一位，例如：
```js
const bmiFormatted = rawBmi.toFixed(1); // 會自動四捨五入
const bmiValue = parseFloat(bmiFormatted); // 分級用這個值
```
為什麼：23.96 應顯示 24.0 並判為「過重」，現在卻顯示 23.9 判為「體重正常」，邊界個案會低判一級。

### 2. 分級要用進位後的值判定
現在 `getBMICategory(bmiValue)` 傳入的是捨去後的值。改為傳入四捨五入後的 `bmiValue`（同上），確保顯示的數字與評語一致。

### 3. 移除 HTML 第 1 行的交接註解
交接文字請只留在 `outbox/` 的 `.md` 交接檔，HTML 裡的 `<!-- 交接：... -->` 請移除，成品保持乾淨。

## 怎樣算做完 / Done looks like
- 新檔存在 `workspace/outbox/20261012-bmi-calculator-v2.html`，第一版檔案保持原樣。
- 自測通過並寫在交接裡：
  - 170cm / 65kg → 22.4「體重正常」
  - 163cm / 63kg → 23.7（rawBMI ≈ 23.66，四捨五入）「體重正常」
  - 170cm / 70kg → 24.2「過重」（確認 24 邊界進位後判級正確）
- 其餘功能（驗證、六級分級、警語、繁中介面）維持與 v1 相同。
- 留一行交接：改了什麼、自測結果、能不能直接用。
