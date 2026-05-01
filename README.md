# ACLS 2025 視覺化辨識卡 v1.1

互動式網頁工具,涵蓋 2025 AHA ACLS 指引的心電圖辨識、急救流程、ECPR 啟動時機、急救用藥、Megacode 練習等。

單檔 HTML(無外部依賴),可直接部署到 GitHub Pages 或本機開啟。

## 內容(8 個分頁)

- **心電圖圖鑑** — 16 種必考心律(SVG 重畫,點擊看辨識重點與處置)
- **死人活人決策樹** — 視覺化急救流程,點節點看詳情
- **ECPR 啟動時機** — 2025 Class 2a 新內容,搭配嘉基系統對應
- **12 導程 STEMI** — 各區域導程與責任血管對照
- **急救用藥** ★ 新增 — 38 種藥物 / 7 大類別,完整劑量、配製、副作用、2025 變動
- **2020 vs 2025 完整差異** — 20 個變動點對照表
- **Megacode 練習** — 12 題情境模擬
- **自我測驗** — 隨機抽 EKG 判讀,localStorage 記錄答對率

## 急救用藥七大類(共 38 種)

- **CPR 期間用藥**(7):Epinephrine、Amiodarone、Lidocaine、Magnesium、Calcium、NaHCO3、Vasopressin
- **心律調節**(6):Adenosine、Atropine、Diltiazem、Verapamil、Esmolol、Procainamide
- **升壓循環支持**(4):Dopamine、Norepinephrine、Dobutamine、Phenylephrine
- **ACS / STEMI Bundle**(7):Aspirin、Clopidogrel、Ticagrelor、Heparin、NTG、Morphine、Alteplase
- **中風 / 溶栓**(2):Tenecteplase ★ 2025 新、Labetalol
- **特殊解毒劑**(7):Naloxone、Flumazenil、Glucagon、IV Lipid、Hydroxocobalamin、Insulin/Glucose、Activated Charcoal
- **RSI / 鎮靜插管**(5):Etomidate、Ketamine、Midazolam、Succinylcholine、Rocuronium

每張藥物卡顯示:中英藥名、主要適應症、速查劑量。點擊看完整內容:適應症、成人/小兒劑量、給藥途徑、配製方式、副作用、禁忌症、易踩雷、2025 更新。

**10 種藥有 2025 變動標記** — 包括 Calcium / Vasopressin / NaHCO3 改 Class 3、Tenecteplase 新增、IV Lipid 升為明確建議、Insulin HIET 主流等。

## 功能

- 全文搜尋(打「VT」、「不穩定」、「房室阻斷」、「Epi」、「升壓」、「腎上腺素」都能找,同時搜心電圖和藥物)
- ★ 收藏標記(localStorage)
- 列印模式(瀏覽器列印按鈕)
- 深色模式(跟隨系統設定)
- 響應式設計(手機/平板/電腦皆適用)

## 部署到 GitHub Pages

### 方法一:新建 repo

```bash
git init
git add index.html README.md
git commit -m "ACLS 2025 v1.1"
git branch -M main
git remote add origin https://github.com/cych05845-jpg/acls-2025.git
git push -u origin main
```

Settings → Pages → Source 選 `main` branch → Save。
訪問 `https://cych05845-jpg.github.io/acls-2025/`。

### 方法二:加到現有 repo 子目錄

```bash
mkdir acls-2025
cp index.html acls-2025/
git add acls-2025
git commit -m "Add ACLS 2025 visual recognition card"
git push
```

## 本機使用

雙擊 `index.html` 直接開啟。或丟到 USB / LINE 給同仁。

## 修改與擴充

所有資料都在單檔 `<script>` 區塊內:

- `EKG_DATA` 陣列:新增/修改心律
- `DRUG_DATA` 陣列:新增/修改藥物
- `DRUG_CATEGORIES` 陣列:調整藥物類別與顏色
- `MEGACODE_SCENARIOS` 陣列:新增情境題
- `FLOW_DETAILS` / `ECPR_DETAILS` 物件:修改流程 modal 內容

## 資料來源

- AHA 2025 CPR & ECC Guidelines (2025/10/22 公告)
- 原 ACLS 筆試破題解析 v.2020.11.24 (黃品叡)
- 急救用藥參考 UpToDate、Lexicomp、AHA Pharmacology Guidelines

## 授權

僅供臨床參考、教學、與個人備考使用。實際操作仍以 AHA 官方指引、院內 SOP 與主治醫師判斷為準。
