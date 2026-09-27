## Hold Shift and Check Checkboxes

實作點擊 checkbox 後按 shift 可以有一鍵選取多個 checkbox 的功能。

## Snippets

```js
const checkboxes = document.querySelectorAll('.inbox input[type="checkbox"]');

let lastChecked;
```

把 HTML 中的 checkbox 選起來，並設置變數作為勾選位置紀錄。

```js
function handleCheck(e) {
	let inBetween = false;
	if (e.shiftKey && this.checked) {
		checkboxes.forEach(checkbox => {
			console.log(checkbox);
			if (checkbox === this || checkbox === lastChecked) {
				inBetween = !inBetween;
				console.log('Staring to check them inBetween');
			}
			if (inBetween) {
				checkbox.checked = true;
			}
		});
	}
	lastChecked = this;
}
```

先檢查是否按著 shift 點選，再從當前點選的 checkbox 一路記到最後一個 checkbox 標記，然後勾選區間內為 true 的 checkbox 就可以了。

## References

- [dwatow](https://github.com/dwatow/JavaScript30/tree/master/10%20Hold%20Shift%20and%20Check%20Checkboxes)
- [dustinhsiao21](https://github.com/dustinhsiao21/Javascript30-dustin/tree/master/10%20-%20Hold%20Shift%20and%20Check%20Checkboxes)
- [guahsu](https://github.com/guahsu/JavaScript30/tree/master/10_Hold-Shift-and-Check-Checkboxes)
