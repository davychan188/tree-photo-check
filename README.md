# 四張相片完整性對比 / Tree Photo Check

離線 HTML 工具：對比樹編號名單與相片檔名，檢查每棵樹是否齊全 Tag、Whole view、Trunk base、Crown。

單檔、無伺服器、無上載相片（拖資料夾只讀檔名）。

## 開法

用瀏覽器直接打開 `index.html`，或 GitHub Pages 指向此資料夾。

## 匯出檔名／_後資料去 Excel

貼完整路徑後撳「檢查」，再用：
- **匯出 Excel（檔名／_後）**：下載 CSV（完整路徑、檔名、樹號、`_` 後資料、判定角度）
- **複製給 Excel**：複製 TSV，喺 Excel `Ctrl+V` 貼上

已係 `TG-T0201_Tag` 呢類統一寫法就唔使理「建議改名」。

## 大量相片／唔好拖資料夾

- 可直接貼 Explorer「複製為路徑」嘅完整路徑（唔同 folder、連引號都得），會自動只取檔名；改名 BAT 會用返完整路徑。
- 撳「選資料夾（只讀檔名）」：只取檔名，唔會上載相，相幾大都 OK。
- Windows 可下載「用路徑匯出檔名.bat」：改 `FOLDER=` 路徑 → 雙擊 → 得 `photo-filenames.txt` → 貼去右邊欄。


## Excel 缺陷文字 ↔ 相片路徑

1. 選「Excel 缺陷文字 ↔ 相片路徑對比」（預設）
2. 名單 2：相片路徑，例如 `TG-T0175_Co-dominant branches.jpg`
3. 名單 3：Excel 貼 **樹號 + 缺陷**（Tab／逗號／空格），例如：
   - `TG-T0175	Co-dominant branches`
   - `T-2225	Leaning`
4. 名單 1 可選（用來過濾範圍）
5. 撳檢查 → 睇對上／唔啱／有 Excel 無相；可下載或複製缺陷對比 CSV

唔再提供改名 CSV／BAT。預設略過 Tag／Whole view／Trunk base／Crown。


## 用法

1. 左欄貼樹編號（一行一個），或拖 .txt。
2. 右欄貼相片檔名，或把相片資料夾拖入（只取檔名）。
3. 按「檢查」。

預設標準四張：

- `T28_Tag`
- `T28_Whole view`
- `T28_Trunk base`
- `T28_Crown`

`wilted crown`、`decay trunk`、`trunk` 視為其他角度，不與上述四張合併。

## 功能

- 矩陣預覽：樹號 × 角度（有／欠／多張）
- 欠相清單、WhatsApp／電郵短訊
- 數字後格式差異（`_Whole view` vs ` Whole view`）
- 數字後格式差異時，可勾選將少數寫法改成多數（預設標準四張），再下載 CSV / BAT
- 過濾 `Thumbs.db`、`._*`、`.DS_Store`、重複副檔名
- 分開統計 JPG / HEIC

## GitHub Pages

Repo 根目錄若就係本資料夾，Settings → Pages → Deploy from branch → `/`。

網址例：`https://<user>.github.io/<repo>/`

## Grok／自動化

此檔可獨立引用。Bot 或腳本只要讀／寫兩個名單文字，邏輯全在瀏覽器端。若要改成 API，可抽出 `parsePhotos` / `classifyType` 到獨立 JS。

## 少數格式改成多數（可選）

檢查後開「數字後格式」分頁：若同一角度有多種寫法（例如 `_whole view` ×20、`wholeview` ×15），可勾選「將少數改成多數」。

- 預設只勾標準四張（Tag / Whole view / Trunk base / Crown）
- 可用「標準四張／全部角度／全部取消」
- 勾選後會更新「建議改名」，並反映在 CSV / BAT 下載

改名目標用**多數寫法本身**（例如多數係 `_whole view` 就改成 `_whole view`，不只硬套 `_Whole view`）。

## 注意

- 改名 BAT 須與相片放同一資料夾執行，先備份。
- 名單 1 與相片樹號寫法要能對上（`T28` 與 `T028` 現時視為不同）。
