# 長家人時性儀表板

網站會優先載入預先產生的 JSON；若 JSON 不存在或版本不符，會自動回退解析 Excel。

## 日常更新方式

1. 將新的 `.xlsx` 月報放進 `data/`（可以使用年度、月份子資料夾）。
2. 提交並推送到 GitHub。
3. GitHub Actions 會自動掃描所有 Excel、產生 `data/manifest.json` 與 `data-json/`，再提交轉檔結果。

不需要手動修改 manifest。同一月份若同時放了部分日期版與較完整版本，系統會採用結束日期較晚的檔案。

本機轉檔與檢查：

```bash
npm install
npm run convert:data
npm run check:data
```
