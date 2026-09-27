## Mouse Move Shadow

利用 textShadow 製作讓文字陰影隨滑鼠位罝偏移的效果。

## Snippets

```js
const x = a.a
const y = a.b

const { a: x, b: y } = a
```

`ES6` 的簡化語法。

```js
function shadow(e) {
	const { offsetWidth: width, offsetHeight: height } = hero;
	let { offsetX: x, offsetY: y } = e;
	if (this !== e.target) {
		x = x + e.target.offsetLeft;
		y = y + e.target.offsetTop;
}
```

移到 `h1(const text)` 區域時，只計算 h1 內的座標，移出 h1 範圍時又恢復正常。所以計算 h1 內的座標時須加上 `e.target.offsetLeft` 及 `e.target.offsetTop`。

`this(e.currentTarget)` 在 JS 中，若 `DOM element` 被事件綁定，`this` 代表的是該 `DOM element`，儘管事件也有綁定到子元素，`this` 還是代表被綁定的那個元素。

`e.target` 則是代表被觸發的那個 `DOM element`，若事件被綁定在巢狀結構的父元件，當觸發的點是子元件時，會回傳子元件的內容。

```js
const xWalk = Math.round((x / width * walk) - (walk / 2));
const yWalk = Math.round((y / height * walk) - (walk / 2));

text.style.textShadow = `
	${xWalk}px ${yWalk}px 0 rgba(255, 0, 255, 0.7),
	${xWalk * -1}px ${yWalk}px 0 rgba(0, 255, 255, 0.7),
	${yWalk}px ${xWalk * -1}px 0 rgba(0, 255, 0, 0.7),
	${yWalk * -1}px ${xWalk}px 0 rgba(0, 0, 255, 0.7)
`;
```

以 `const walk = 100` 為例，先把 `(實際的位置 / 全部的長度) * 100 - (100 / 2)`，這樣會以中心點為 (0.0)，左上及右下分別為 (-50, -50) 及 (50,50) 。

動畫顯示用 `text.style.textShadow` 參數分別代表 `x, y, blur, color(rgba)`。

`Math.round()` 使數字顯示到個位數。

## References

- [dwatow](https://github.com/dwatow/JavaScript30/tree/master/16%20Mouse%20Move%20Shadow)
- [dustinhsiao21](https://github.com/dustinhsiao21/Javascript30-dustin/tree/master/16%20-%20Mouse%20Move%20Shadow)
- [guahsu](https://github.com/guahsu/JavaScript30/tree/master/16_Mouse-Move-Shadow)
