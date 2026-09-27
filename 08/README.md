## Fun with HTML5 Canvas

使用 HTML5 的 Canvas 和 JS 來製作一個畫布，並有改變顏色和粗細的效果。

## Snippets

```js
const canvas = document.querySelector('#draw');
const ctx = canvas.getContext('2d');

canvas.width = window.innerWidth;
canvas.height = window.innerHeight;
```

`getContext('2d')` 設定畫布內容為 2d 繪圖。

`innerWidth` 不包括 border, padding 等範圍。

`outerWidth` 包括 border, padding 等範圍。

`width` 只有該 DOM Element 等範圍。

`height` 也是同理。

```js
ctx.strokeStyle = '#555';
ctx.lineJoin - 'round';
ctx.lineCap = 'round';
ctx.lineWidth = 100;
```

`ctx.strokeStyle` 定義繪畫的顏色。

`ctx.lineJoin` 定義兩線相交時的拐角。

`ctx.lineCap` 定義結束端點樣式。

`ctx.lineWidth` 定義寬度。

```js
canvas.addEventListener('mousedown', (e) => {
	isDrawing = true;
	[lastX, lastY] = [e.offsetX, e.offsetY];
});

canvas.addEventListener('mousemove', draw);
canvas.addEventListener('mouseup', () => isDrawing = false);
canvas.addEventListener('mouseout', () => isDrawing = false);
```

`mousedown` 按下滑鼠。

`mouseup` 放開滑鼠。

`mousemove` 移動滑鼠。

`mouseout` 滑鼠移開視窗。

```js
ctx.beginPath();
ctx.moveTo(lastX, lastY);
ctx.lineTo(e.offsetX, e.offsetY);
ctx.stroke();
```

`ctx.beginPath()` 當作繪畫啟動。

`ctx.moveTo(a,b)` 當作起始位置。

`ctx.lineTo(a,b)` 當作終點位置。

`ctx.stroke()` 代表繪製已定義的路徑。

`e.offsetX`, `e.offsetY` 代表回傳事件的當前座標。

## References

- [dwatow](https://github.com/dwatow/JavaScript30/tree/master/08%20Fun%20with%20HTML5%20Canvas)
- [dustinhsiao21](https://github.com/dustinhsiao21/Javascript30-dustin/tree/master/08%20-%20Fun%20with%20HTML5%20Canvas)
- [guahsu](https://github.com/guahsu/JavaScript30/tree/master/08_Fun-with-HTML5-Canvas)
- [a90100](https://github.com/a90100/JavaScript30/tree/master/08%20-%20Fun%20with%20HTML5%20Canvas)
