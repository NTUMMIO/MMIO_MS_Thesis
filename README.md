# MMIO 論文 LaTeX 模板 README

> **適用對象**：MMIO 實驗室碩博士論文撰寫  
> **來源**：本模板參考並修訂自 [mediaic/NTU_MS_Thesis](https://github.com/mediaic/NTU_MS_Thesis.git)  
> **規範依據**：此模板以台大論文提交系統「學位論文上傳手冊.pdf / Thesis_Guide.pdf」之2025年版本為準  
> **重要限制**：**本 LaTeX 模板目前不支援中文輸入**（中文頁面請於輸出 PDF 後依照「編輯頁面」處理）

---

## 目錄
- [功能與特色](#功能與特色)
- [環境需求](#環境需求)
- [專案結構](#專案結構)
- [檔案說明](#檔案說明)
- [快速開始](#快速開始)
- [引用與參考文獻](#引用與參考文獻)
- [圖表、演算法與方程式](#圖表演算法與方程式)
- [編輯頁面（重要）](#編輯頁面重要)
- [doc 資料夾檔案用途與插入位置對照](#doc-資料夾檔案用途與插入位置對照)
- [常見問題](#常見問題)
- [授權與致謝](#授權與致謝)

---

## 功能與特色
- 依據 NTU 論文上傳手冊之版面規範進行設計（前頁、章節、附錄等）。
- 內含常用排版示例（引用、圖表、演算法、方程式）可直接套用。
- **英文撰寫流程順暢**；中文頁面改以 **PDF 編輯頁面** 完成（見下文）。

---

## 環境需求
- TeX 發行版：**TeX Live 2023+** 或 **MiKTeX 25+**
- 編譯工具：`latexmk`（建議），或 `pdflatex` / `bibtex`
- 編輯器（擇一）：VS Code（LaTeX Workshop）、TeXstudio、Texmaker 等

---

## 專案結構
```text
.
├─ thesis.tex                # 主檔案（定義前頁、正文、附錄等）
├─ macro.tex                 # 套件與自訂指令（通常不需修改）
├─ thesis.bib                # 參考文獻（BibTeX）
├─ inc/                      # 各章節分檔
│  ├─ Template.tex           # 常用排版示例（引用/圖表/演算法/方程式）
│  ├─ 0_abbreviations/...
│  ├─ 0_abstract/...
│  ├─ 1_introduction/...
│  ├─ 2_related_works/...
│  ├─ 3_materials_methods/...
│  ├─ 4_results/...
│  ├─ 5_discussion/...
│  ├─ 6_conclusion/...
│  └─ 7_appendix/...
└─ doc/                      # 學校提供或需替換之頁面檔
   ├─ Acknowledgement
   ├─ Approval
   ├─ Chinese Abstract
   ├─ Cover
   ├─ Cover_with_side
   ├─ NTU_watermark
   └─ THESISSAMPLE
```

---

## 檔案說明
- **`thesis.tex`**：整體文件入口；設定前置頁、章節匯入（`\input{inc/...}`）、附錄等。
- **`inc/`**：章節內容分檔管理（abbreviations、abstract、introduction、related works、materials and methods、results、discussion、conclusion、appendix）。
- **`inc/Template.tex`**：常用環境與語法示例（圖表、演算法、方程式、引用）；建議先閱讀並比照使用。
- **`thesis.bib`**：BibTeX 參考文獻庫。
- **`macro.tex`**：套件載入與巨集定義，**一般不需修改**。
- **`doc/`**：學校制式頁面與浮水印素材，供 **輸出後 PDF 編輯頁面** 使用。

---

## 快速開始
1. **撰寫內容**  
   - 於 `inc/` 之各章節檔撰寫英文內容。  
   - 在 `inc/0_abbreviations/list_of_abbreviations.tex` 依照範例格式加入縮寫名稱。
   - 於 `thesis.bib` 加入BibTex格式之參考資料文獻。  

2. **（必做）編輯頁面**  
   依「學位論文上傳手冊」於 Acrobat Pro 完成 **封面/中文摘要/致謝** 與 **浮水印（校徽、DOI）** 等作業（見下節）。

---

## 引用與參考文獻
- 於 `thesis.bib` 新增 BibTeX 條目，例：
  ```bibtex
  @book{Cherry_2006_PET,
    author = {Cherry, Simon R. and Dahlbom, Magnus},
    title = {PET: Physics, Instrumentation, and Scanners},
    publisher = {Springer},
    address = {New York, NY},
    DOI = {10.1007/0-387-34946-4_1},
    url = {http://dx.doi.org/10.1007/0-387-34946-4_1},
    year = {2006},
    type = {Book}
  }
  @article{Zhou_2004_SSIM,
    author  = {Zhou, Wang and Bovik, Alan C. and Sheikh, Hamid R. and Simoncelli, Eero P.},
    title   = {Image Quality Assessment: From Error Visibility to Structural Similarity},
    journal = {IEEE Transactions on Image Processing},
    year    = {2004},
    volume  = {13},
    number  = {4},
    pages   = {600--612}
  }
  ```
- 文中引用使用 `\cite{Cherry_2006_PET}`（或依模板已載入之引用套件調整）。
- 變更/新增文獻後，請重新執行 **BibTeX 流程**。

---

## 圖表、演算法與方程式
- 範例皆收錄於 `inc/Template.tex`：  
  - **圖表**：`figure`  
  - **表**：`table`  
  - **演算法**： `algorithm`  
  - **方程式**：`equation`  
- 建議：複製範例區塊 → 修改標題/標號/標註 → 引用於正文。

---

## 編輯頁面（重要）
> 本模板 **不支援中文輸入**。**封面（Cover）**、**中文摘要（Chinese Abstract）**、**致謝（Acknowledgement）** 等中文或學校制式頁面，請於輸出 `thesis.pdf` 後以 **Adobe Acrobat Pro** 進行替換／插入與 **浮水印** 設定。

**步驟：**
0. 步驟依「學位論文上傳手冊」（頁碼格式、頁面順序、浮水印頁範圍與樣式）。  
1. 以 **Adobe Acrobat Pro** 開啟 `thesis.pdf`。  
2. 進入 **工具 ▸ 組織頁面（Organize Pages）**。  
3. **插入封面**：將 `doc/Cover` 插入至文件最前方（不加入頁碼）。  
4. **替換頁碼 i–ii（羅馬數字）為致謝**：以 `doc/Acknowledgement` 取代。  
5. **替換頁碼 iii–iv（羅馬數字）為中文摘要**：以 `doc/Chinese Abstract` 取代。  
6. **校徽與 DOI 浮水印**：  
   - **校徽**：**工具 ▸ 編輯 PDF ▸ 浮水印 ▸ 新增**，選擇 `doc/NTU_watermark`（圖檔）並依手冊規定位置/透明度/套用頁面範圍設定。  
   - **DOI 碼**：同上以 **浮水印** 新增（可用文字或圖檔），內容與位置請依手冊規範。  
7. 依「學位論文上傳手冊」設定保全。  
8. 依「學位論文上傳手冊」逐項檢查。  

> **提醒**：實際插入/替換頁範圍與樣式以「學位論文上傳手冊」之**最新規定**為準；若手冊版本更新，請據以調整。

---

## 常見問題
- **為何不能直接輸入中文？**  
  本模板未啟用中文字型/排版套件，僅支援英文編譯。中文頁面改以 **PDF 編輯頁面** 完成，以確保相容性與版面符合學校規範。

- **參考文獻樣式如何更改？**  
  本模板預設 BibTeX 流程；如需改動引用樣式，請自行調整相關套件與 `.bst` 檔並完整測試。

- **頁碼 i、ii、iii… 如何確認？**  
  以 Acrobat Pro 檢視縮圖與頁碼標註，並比照學校手冊之前置頁順序與標示方式。

---

## 授權與致謝
- 本模板**參考並修訂**自：`mediaic/NTU_MS_Thesis`。  
- 使用與再散布請同時遵循本專案與上游專案之授權條款；若需授權細節，請查閱各專案的授權聲明。  
- 感謝 MMIO 實驗室成員之建議與回饋。

---

**最後提醒**：請以 **「學位論文上傳手冊.pdf / Thesis_Guide.pdf」** 的**最新版本**為最終依據，編譯與編輯頁面完成後務必逐條檢查。祝順利完稿！
