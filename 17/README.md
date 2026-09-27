## Sort Without Articles

介紹和複習陣列的排序。

## Snippets

```js
function strip(bandName) {
  return bandName.replace(/^(a |the |an)/i, "").trim();
}
```

使用 replace 和正規表示式將包含 a, the, an 開頭的文字替換為空白。

```js
const sortedBands = bands.sort((a, b) => (strip(a) > strip(b) ? 1 : -1));
```

對目標陣列進行篩選與排序

```js
document.querySelector("#bands").innerHTML = sortedBands
  .map((band) => `<li>${band}</li>`)
  .join("");
```

最後使用 map 與 join 來組成 `<li>` 元素放置。

## References

- [dwatow](https://github.com/dwatow/JavaScript30/tree/master/17%20Sort%20Without%20Articles)
- [dustinhsiao21](https://github.com/dustinhsiao21/Javascript30-dustin/tree/master/17%20-%20Sort%20Without%20Articles)
- [guahsu](https://github.com/guahsu/JavaScript30/tree/master/17_Sort-Without-Articles)
