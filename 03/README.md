## CSS Variables

用 JS 和 CSS 製作一個即時的圖片濾淨效果，可以調整內邊距、模糊、邊框色。

## Snippets

`input` 的 `type="range"` 會呈現可左右移動的滑桿。

CSS 的 `:root` 是 DOM 的根元素，變數寫法為 `--variable` ，用 `var(--variable)` 的方式來取得。

`filter:blur()` 為模糊度，還有 `opacity()` 為透明度。

```js
function handleUpdate() {
	const suffix = this.dataset.sizing || '';
	document.documentElement.style.setProperty(`--${this.name}`, this.value + suffix);
}
```

`this.dataset` 會出現所有 `data-` 的項目及值。若要選取 `data-sizing` 的值，使用`this.dataset.sizing` 處理。

在取到目標的值之後，還需要加上 `px` 值才能運作，因顏色沒有單位，所以為空，避免報錯。

## References

- [dwatow](https://github.com/dwatow/JavaScript30/tree/master/03%20CSS%20Variables)
- [dustinhsiao21](https://github.com/dustinhsiao21/Javascript30-dustin/tree/master/03%20-%20CSS%20Variables)
- [guahsu](https://github.com/guahsu/JavaScript30/tree/master/03_CSS-Variables)
- [a90100](https://github.com/a90100/JavaScript30/tree/master/03%20-%20CSS%20Variables)
