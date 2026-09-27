## Flex Panel Gallery

用 CSS 和 JS 製作一個有展開圖片效果的網站。

## Snippets

```css
<div class="panel">
	<h1>Hello</h1> # 選取
	<p>World</p> # 選取
	<div> # 選取
		<span>Test</span> # 不會選取
	</div>
</div>
```

`.panel > *` 會選取 `.panel` 下的所有直接子元素，也可以指定元素，例如 `.panel > div` 就只會選取直接子元素中，是 `div` 的那些。

```css
<div class="panel">
	<h1>Hello</h1> # 選取
	<p>World</p> # 選取
	<div> # 選取
		<span>Test</span> # 選取
	</div>
</div>
```

若無 `>` 則 `.panel *` 會選取所有後代子元素。

`this.classList.toggle()` 可以像開關一樣偵測 HTML 的 CSS 元素，如果沒有就增加，有就刪除掉。

個別瀏覽器有不同的判斷，例如 `transition: flex 0.7s...` 這段在 sarafi 是 `flex`，其他瀏覽器為 `flex-grow`，所以利用 `.includes('flex')` 來判斷，避免其中一方瀏覽器抓不到值。

## References

- [dwatow](https://github.com/dwatow/JavaScript30/tree/master/05%20Flex%20Panel%20Gallery)
- [dustinhsiao21](https://github.com/dustinhsiao21/Javascript30-dustin/tree/master/05%20-%20Flex%20Panel%20Gallery)
- [guahsu](https://github.com/guahsu/JavaScript30/tree/master/05_Flex-Panel-Gallery)
