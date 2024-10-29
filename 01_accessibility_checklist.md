# 網站無障礙設計檢核表

本檢核表旨在幫助您檢查網站的無障礙設計是否符合標準。

## 語義化 HTML

- [ ] 是否使用正確的 HTML 標籤（如 `<header>`, `<nav>`, `<main>`, `<footer>`）來定義結構？
- [ ] 是否避免過度依賴 `<div>` 和 `<span>` 來布局？

**範例：**
```html
<header>
  <h1>網站標題</h1>
</header>
<nav>
  <ul>
    <li><a href="#home">首頁</a></li>
    <li><a href="#about">關於我們</a></li>
  </ul>
</nav>
<main>
  <section>
    <h2>主要內容</h2>
    <p>這是網站的主要內容。</p>
  </section>
</main>
<footer>
  <p>聯絡我們: email@example.com</p>
</footer>
```

## 提供替代文字 (alt text)

- [ ] 所有圖像是否都有適當的替代文字描述？

**範例：**
```html
<img src="image.jpg" alt="描述圖片的內容">
```

## 使用 ARIA 標籤

- [ ] 是否使用 ARIA 標籤來輔助非語義化的互動元素？

**範例：**
```html
<button aria-label="關閉菜單">X</button>
```

## 定位點(導盲磚)

- [ ] 是否至少包含上方功能區塊`alt+U`、中央內容區塊`alt+U`、頁尾網站資訊`alu+z`
- [ ] 樣式是否為:::，且可被 `ctrl+F `搜尋
- [ ] 是否有把快速鍵於網站導覽頁(sitemap)以文字說明呈現
- [ ] 導盲磚內是否有title 說明該區域為何
**範例：**
```html
<a href="#header-container" accesskey="U" class="visually-hidden" title="網頁導覽區">:::</a>
```

```css
// 無障礙導盲磚隱藏樣式(此待驗證，但無障礙網站自己也使用與背景一樣顏色藉此隱藏)
.visually-hidden {
    position: absolute;
    width: 1px;
    height: 1px;
    margin: -1px;
    padding: 0;
    border: 0;
    clip: rect(0, 0, 0, 0);
    overflow: hidden;
    white-space: nowrap;
}
```

## 鍵盤可導航

- [ ] 所有互動元素是否可以用鍵盤操作？ 包含按鈕、連結
- [ ] 焦點順序是否合理？
- [ ] 焦點元素是否有可見的樣式提示？

**範例：**
```html
<a href="#content" tabindex="1">跳到內容</a>

```

 ```css
 // 可見樣式 css 範例 
a:focus,
button:focus {
    outline: 3px dashed $primary-color;
}
```


## 對比度與可讀性

- [ ] 文字與背景之間是否有足夠的對比度？
- [ ] 是否避免使用過於相近的顏色組合？

**範例：**
```css
body {
  background-color: #ffffff;
  color: #000000; /* 高對比度的文字與背景 */
}
```

## 可縮放文字

- [ ] 文字大小是否可以通過瀏覽器縮放進行調整？
- [ ] 是否避免使用固定尺寸(px)的文字？

**範例：**
```css
body {
  font-size: 100%; /* 使用相對大小，避免固定 px 值 */
  font-size: 1rem;
}
```

## 可理解的表單設計

- [ ] 表單是否使用標籤 (`<label>`) 與輸入欄位配合？
- [ ] 是否為必填欄位提供適當的提示？

**範例：**
```html
<label for="name">姓名</label>
<input type="text" id="name" name="name" aria-required="true">
```

---

依據這個檢核表逐步檢查您的網站，確保其符合無障礙設計的需求。
