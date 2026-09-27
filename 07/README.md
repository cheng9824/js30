## Array Cardio Day 2

練習使用 `some()`, `every()`, `find()`, `findIndex()` 等陣列方法。

## Snippets

`some()` 會將陣列中的資料進行判斷，有一筆通過則回傳 `true` 並結束。

`every()` 對陣列中的資料進行判斷，有一筆不符合則回傳 `false` 並結束。

`find()` 會對陣列中的資料進行判斷，返回第一筆符合條件的值。

`findIndex()` 對陣列中的資料進行判斷，返回符合條件的索引值。

```js
const newComments = [
...comments.slice(0, index),
...comments.slice(index + 1)
];
```

因為 `slice` 回傳 array object 所以數值會變成 `[Array[], Array[]]` ，可以利用 `spared` 省略符號 `...` 展開陣列後透過 `slice()` 組合陣列來解決。

## References

- [dwatow](https://github.com/dwatow/JavaScript30/tree/master/07%20Array%20Cardio%20Day%202)
- [dustinhsiao21](https://github.com/dustinhsiao21/Javascript30-dustin/tree/master/07%20-%20Array%20Cardio%20Day%202)
- [guahsu](https://github.com/guahsu/JavaScript30/tree/master/07_Array-Cardio-Day-2)
