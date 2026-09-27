## JS and CSS Clock

用 CSS 和 JS 來模擬一個時鐘。

## Snippets

横線使用 `transform-origin: 100%` 將軸心移到最右側，接 `transform: rotate(90deg)` 就可以打直。

`transition` 可以增加動畫感，也就是發生變化後，在指定秒數平滑完成。

`transition-timing-function` 設定物件在變形其間的變形速度。

用 `now = new Date()` 來取得分、秒、時。

```js
const secondsDegrees = ((seconds / 60) * 360) + 90;

const minsDegrees = ((mins / 60) * 360) + ((seconds / 60) * 6) + 90;

const hourDegrees = ((hour / 12) * 360) + ((mins / 60) * 30) + 90;
```

各自加上已旋轉的 90 度後，分，時針還要算上每秒、分的指針移動度數。

```js
function setRotate(deg, hand) {
	if (deg === 90) {
	hand.style.transition = 'all 0s';
} else {
	hand.style.transition = 'all 0.05s';
} 
return `rotate(${deg}deg)`;
}
```

當角度歸零時指針會抖動，是因為從 59 秒的 400 多度一下轉回 0 秒的 90 度，動畫特效造成的結果，只要角度歸零時把動畫特效取消就可以了。

定時器 `setInterval(setDate, 1000)` 來設定每次執行的函數與時間。

## References

- [dwatow](https://github.com/dwatow/JavaScript30/tree/master/02%20JS%20and%20CSS%20Clock)
- [dustinhsiao21](https://github.com/dustinhsiao21/Javascript30-dustin/tree/master/02%20-%20JS%20and%20CSS%20Clock)
- [guahsu](https://github.com/guahsu/JavaScript30/tree/master/02_JS-and-CSS-Clock)
- [a90100](https://github.com/a90100/JavaScript30/tree/master/02%20-%20JS%20and%20CSS%20Clock)

