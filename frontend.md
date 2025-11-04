# Hahow Frontend Engineer 徵才小專案

我們希望透過這份專案了解你的程式設計、程式碼品質、文件撰寫、溝通等等能力，期待你和我們分享實作這份小專案的各種考量與設計，不僅是完成需求而已。
請閱讀以下的需求完成這份小專案。

## 必要項目

- 請遵守 **Wireframe** 及 **頁面需求** 實作這個專案
- 請使用 React 進行開發
- 使用 git / GitHub 來做整個專案的版本控管
- 請將小專案上傳到 GitHub， **不接受以雲端硬碟或信件夾帶壓縮檔的形式繳交作業**
- repo 中需要 **包含一份 README 文件**，說明以下項目：
  - 該如何執行完成的專案
  - 專案的資料夾架構、Application 的邏輯架構，說明你的設計理念
  - 對於所有使用到的第三方 library 的理解，以及為何想在這個專案中使用它
  - 你在程式碼中寫註解的原則，遇到什麼狀況會寫註解
  - 在這份專案中你遇到的困難、問題，以及解決的方法

## 加分項目

- 使用 CSS-in-JS library
- 任何讓專案更加完整的功能
- 任何可提升程式碼品質（可讀性、可維護性、效能等）的做法
- 任何你覺得可以讓網頁更 UX friendly 的功能
- 若有使用 AI 輔助開發，請描述使用哪些 AI 工具、什麼情境下使用、如何和 AI 互動等

若有實作加分項目，也請在 README 文件中說明。

## 頁面需求

- 整個專案會需要兩個頁面，當使用者重新整理或直接輸入 URL 都需正常運作
  - Hero List Page (網址: `/heroes`)
  - Hero Profile Page (網址: `/heroes/:heroId`)
- "Hero List Page"、"Hero Profile Page" 都有一個 "Hero List" 在頁面上水平置中 (API: `GET https://hahow-recruit.herokuapp.com/heroes`)
- "Hero List" 上的元素我們稱為 "Hero Card"，在 "Hero List" 中由左到右排列，如果在小尺寸螢幕上列表中的元素超出畫面就自動往下排列
- "Hero Card" 必須包含圖片和名字，且是可以點擊的連結
- "Hero Card" 連結會連到單一 Hero 的 "Hero Profile Page"，"Hero List" 依然在相同位置，並且不因切換連結重新 render
- 當在 "Hero Profile Page" 時要將現在所選中的 "Hero Card" 用不同的顏色或圖案標示出來
- "Hero Profile Page" 中，在 "Hero List" 底下會有一個 "Hero Profile"
- "Hero Profile" 會顯示 Hero 的能力值 (API: `GET https://hahow-recruit.herokuapp.com/heroes/:heroId/profile`)，並且在數值左右各有一個按鈕，負責做增減功能，另外有一個顯示剩餘的能力點數的地方，一開始預設值是 0
- "Hero Profile" 最下方有一個儲存按鈕，按下按鈕後，會將現在設定的能力值提交更新 server 上的資料 (API: `PATCH https://hahow-recruit.herokuapp.com/heroes/1/profile`)，送出的能力值總和必須與拿到的時候相同
- Hero 能力值不能小於零

## Wireframe

![](assets/hero-list-page.png)

![](assets/hero-profile-page.png)

## 我們所提供的資料及 API

### List Heroes [GET] `https://hahow-recruit.herokuapp.com/heroes`

**Request**

```bash
curl -H "Accept: application/json" -H "Content-Type: application/json" -X GET https://hahow-recruit.herokuapp.com/heroes
```

**Response 200**

```
[
  {
    "id": string
    "name": string
    "image": string
  }
]
```

### Single Hero [GET] `https://hahow-recruit.herokuapp.com/heroes/:heroId`

**Request**

```bash
curl -H "Accept: application/json" -H "Content-Type: application/json" -X GET https://hahow-recruit.herokuapp.com/heroes/1
```

**Response 200**

```
{
  "id": string
  "name": string
  "image": string
}
```

### Profile of Hero [GET] `https://hahow-recruit.herokuapp.com/heroes/:heroId/profile`

**Request**

```bash
curl -H "Accept: application/json" -H "Content-Type: application/json" -X GET https://hahow-recruit.herokuapp.com/heroes/1/profile
```

**Response 200**

```
{
  "str": number
  "int": number
  "agi": number
  "luk": number
}
```

### Patch Hero's Profile [PATCH] `https://hahow-recruit.herokuapp.com/heroes/:heroId/profile`

**Request**

```bash
curl -X PATCH -H "Content-Type: application/json" -d '{ "str": 6, "int": 7, "agi": 7, "luk": 5 }' "https://hahow-recruit.herokuapp.com/heroes/1/profile"
```

**Response 200**

```plain
OK
```

## 最後

當你完成的時候，請將你的 GitHub repo 連結 e-mail 給我們。

同時我們也認為在程式開發的過程中溝通是很重要的，所以如果過程中你有任何問題，不論是看不懂我們所寫的文件，或是對於我們提供的 API 有疑問，都歡迎直接在 Slack Channel 和我們討論。
