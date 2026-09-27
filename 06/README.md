## Type Ahead

製作一個有即時搜尋、顯示對應內容效果的網站。

## Snippets

`fetch() api` 是內建的 web api，使用它來取得 json 檔，可以參考這兩個 [Window: fetch() method](https://developer.mozilla.org/en-US/docs/Web/API/Window/fetch), [Using the Fetch API](https://developer.mozilla.org/en-US/docs/Web/API/Fetch_API/Using_Fetch) 的解說

`RegExp()` 為正規表達式的參數，g 代表 global，i 代表 insensitive 不分大小寫。

```js
function numberWithCommas(x) {
	return x.toString().replace(/\B(?=(\d{3})+(?!\d))/g, ',');
}
```

處理人口數字的部分用了千位分隔符，詳細解說可以看[這個題問](https://ithelp.ithome.com.tw/questions/10195924)。

## References

- [dwatow](https://github.com/dwatow/JavaScript30/tree/master/06%20Type%20Ahead)
- [dustinhsiao21](https://github.com/dustinhsiao21/Javascript30-dustin/tree/master/06%20-%20Type%20Ahead)
- [guahsu](https://github.com/guahsu/JavaScript30/tree/master/06_Type-Ahead)
- [a90100](https://github.com/a90100/JavaScript30/tree/master/06%20-%20Type%20Ahead)
