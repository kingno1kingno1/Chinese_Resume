# 中文履歷模板使用說明

## Overleaf 上的使用方式

1. **上傳檔案**：手動上傳以下檔案到 Overleaf 新專案：
   - `resume.tex` (主檔案)
   - `awesome-cv.cls` (樣式檔案)
   - `resume/` 目錄下的所有 .tex 檔案
   
2. **編譯設定**：在 Overleaf 中**必須**選擇 **XeLaTeX** 編譯器

3. **字體設定**：已使用基本中文字體 SimSun/SimHei，應該可以在 Overleaf 上正常顯示

## 重要修改事項

### 最新字體優化 (版本 3.0) - 使用 xeCJK 自動檢測
- 使用 `xeCJK` 套件的自動字體檢測功能
- 設定多重字體備援機制，提高相容性
- 啟用 `AutoFallBack` 讓 xeCJK 自動選擇可用字體
- 優化中文標點符號和斷行處理

### 字體處理機制
本版本使用 `xeCJK` 套件的先進功能：
1. **自動檢測**：xeCJK 會自動找到系統中可用的中文字體
2. **多重備援**：設定了多個備援字體，包括 Noto Sans、FandolSong、SimSun 等
3. **假粗體**：當粗體字型不可用時，自動生成假粗體效果

### 排版結構優化
- 將巢狀列表改為單一層級，避免版面問題
- 調整 `cventry` 間距設定
- 優化 `cvitems` 環境的項目間距
- 增加表格行高避免文字重疊

## 編輯內容

### 個人資訊 (resume.tex)
```tex
\name{齊}{乃嘉}  % 修改姓名
\position{後端工程師 | AI/ML 開發者}  % 修改職位
\mobile{+886 970337720}  % 修改電話
\email{kingno1kingno1@gmail.com}  % 修改信箱
```

### 各區塊檔案
- **工作經歷**：`resume/experience.tex`
- **學歷**：`resume/education.tex`
- **專案**：`resume/projects.tex`
- **技能**：`resume/skills.tex`
- **證照**：`resume/certificate.tex`

## 故障排除

### 如果編譯失敗：
1. 確認使用 **XeLaTeX** 編譯器（不是 pdfLaTeX）
2. 檢查所有檔案都已正確上傳
3. 新版本使用 xeCJK 自動字體檢測，應該能自動找到可用字體
4. 如果仍有字體問題，xeCJK 會自動切換到備援字體

### 如果 xeCJK 自動檢測失敗：
可以手動指定字體，在 resume.tex 中修改：
```tex
\setCJKmainfont{SimSun}  % 使用基本字體
```
或
```tex
\setCJKmainfont{AR PL UMing TW}  % 使用 Overleaf 預設字體
```

### 如果文字重疊：
- 本版本已經優化間距設定，應該可以解決重疊問題
- 如仍有問題，可調整 awesome-cv.cls 中的 `\linespread` 值

## 版本記錄
- v3.0: 使用 xeCJK 自動字體檢測，提高相容性和穩定性
- v2.0: 簡化字體設定，優化中文排版
- v1.0: 初始中文化版本