# Hahow iOS Engineer 面試小專案

請實作一個列表畫面的 APP，其中包含課程以及文章區塊，並寫文件或註解來解釋設計考量。除了指定需求外，可以自由設計 model 和 UI 來提供更好的體驗。

## 技術規定

- Deployment Target 為 iOS 15.0。
- 請使用 Swift 和 SwiftUI（或是 UIKit）開發。
- 需同時支援 iPhone 和 iPad。
- 可使用第三方 library。
- 可使用 SPM 或任何第三方管理工具。
- 請寫文件或註解來解釋你的設計考量。

## 需求

請實作一個列表畫面的 APP，其中包含課程以及文章區塊，需求如下：

#### 資料

- 請設計一個 Data Loader 的抽象層來提供課程資料。
- 請用專案中提供的 JSON file 實作上述 Data Loader 的一個實例。
  - courses.json → 課程區塊數據
  - articles.json → 文章區塊數據
- 課程型態分為「募資中」與「已開課」兩種，對應到數據中的：
  - 「募資中」→ `INCUBATING`
  - 「已開課」→ `PUBLISHED`
- 達標進度計算方式：

  ```
  numSoldTickets / successCriteria.numSoldTickets
  ```

- 非同步取得課程數據以及非同步取得文章數據後才會刷新畫面

#### UI 設計

- 在 iPhone 上
  - 課程區塊至多顯示 3 堂課程，其中第 1 堂課程的設計樣式為大圖，其餘為小圖。
  - 文章區塊至多顯示 3 篇文章。
  - 沒有課程就不顯示課程區塊。
  - 沒有文章就不顯示文章區塊。
- 在 iPad 上
  - 課程區塊至多顯示 5 堂課程，其中第 1 堂課程的設計樣式為大圖，其餘為小圖，第二項開始 1 個 row 會顯示 2 堂課程。
  - 文章區塊至多顯示 6 篇文章，1 個 row 會顯示 2 篇文章。
  - 沒有課程就不顯示課程區塊。
  - 沒有文章就不顯示文章區塊。
- iPhone 只需要支援 portrait 豎直方向，iPad 需要全方向 & 分割畫面。
- 課程和文章標題至多 2 行。
- 提示
  - 不用在意卡片尺寸、顏色、間距等細節，請將重點放在如何排版。（你仍然可以盡量符合示意圖）
  - 你可以用 `TableView` 、 `CollectionView` 或任何你熟悉的方式實作。

iPhone 畫面示意 | iPad 畫面示意
--- | ---
![iPhone](https://github.com/hahow/hahow-recruit/assets/15129081/4cdd7dae-3b47-4cc5-869c-5e42844cf25a) | ![iPad](https://github.com/hahow/hahow-recruit/assets/15129081/d400dc70-9d50-41b9-8ac6-43194778baae)

## 提交

- 請下載或 fork Hahow iOS Engineer 面試題目初始專案（[傳送門](https://github.com/hahow/iOS-recruit-project)）。
- 請將成果上傳至 GitHub 並直接提供 repo 連結。

