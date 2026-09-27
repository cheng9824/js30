## LocalStorage

建立一個具有 LocalStorage 功能的選單網頁。

## Snippets

```js
function addItem(e) {
	e.preventDefault();
	const text = (this.querySelector('[name=item]')).value;
	const item = {
		text,
		done: false
	};

	items.push(item);
	populateList(items, itemsList);
	localStorage.setItem('items', JSON.stringify(items));
	this.reset();
}
```

加上 `preventDefault()` 防止每次都重整網頁，後用 `querySelector` 來選取 form 的 input 值。

將 items 的資訊存在 localStorage 中一個叫做 items 的自訂物件中，存入的物件或陣列須透過 `JSON.stringify` 轉為字串，因 localStorage 中的值是 string，直接存只會得到 "object object" 的字串。

宣告新增要存入的物件，再利用 `this.reset()` 來清空輸入欄位。

```js
function populateList(plates = [], platesList) {
	platesList.innerHTML = plates.map((plate, i) => {
		return `
			<li>
				<input type="checkbox" data-index=${i} id="item${i}" ${plate.done ? 'checked' : ''} />
				<label for="item${i}">${plate.text}</label>
			</li>
			`;
		}).join('');
	}
```

用 map 搭 join 來組成字串，並顯示在 html 的清單 ul 中。

```js
function toggleDone(e) {
	if (!e.target.matches('input')) return;
	const el = e.target;
	const index = el.dataset.index;
	items[index].done = !items[index].done;
	localStorage.setItem('items', JSON.stringify(items));
	populateList(items, itemsList);
}
```

偵測 `input(checkbox)` 動作，取得 checkbox 的 data-index 值，並利用 ! 使 done 的能切換，後將狀態寫入 localStorage 中，更新列表。

## References

- [dwatow](https://github.com/dwatow/JavaScript30/tree/master/15%20LocalStorage)
- [dustinhsiao21](https://github.com/dustinhsiao21/Javascript30-dustin/tree/master/15%20-%20LocalStorage)
- [guahsu](https://github.com/guahsu/JavaScript30/tree/master/15_LocalStorage)
- [a90100](https://github.com/a90100/JavaScript30/tree/master/15%20-%20LocalStorage)
