## Adding Up Time With Reduce

使用 `map()`, `reduce()` 來計算影片時數。

## Snippets

```js
const timeNodes = Array.from(document.querySelectorAll("[data-time]"));

const seconds = timeNodes
  .map((node) => node.dataset.time)
  .map((timeCode) => {
    const [mins, secs] = timeCode.split(":").map(parseFloat);
    return mins * 60 + secs;
  })
  .reduce((total, vidSeconds) => total + vidSeconds);

let secondsLeft = seconds;
```

取出元素中的 `data-time` 資料後，用解構賦值的方式分別得到 `split(':')` 的分與秒，再透過 `map()` 執行 `parseFloat` 將字串轉數值，回傳轉換後的總秒數，用 `reduce()` 來加總每次執行結果。

```js
const hours = Math.floor(secondsLeft / 3600);
secondsLeft = secondsLeft % 3600;

const mins = Math.floor(secondsLeft / 60);
secondsLeft = secondsLeft % 60;

console.log(hours, mins, secondsLeft);
```

總秒數進行時、分、秒的計算，使用 `Math.floor` 取整和 % 操作餘數。

## References

- [dustinhsiao21](https://github.com/dustinhsiao21/Javascript30-dustin/tree/master/18%20-%20Adding%20Up%20Times%20with%20Reduce)
- [guahsu](https://github.com/guahsu/JavaScript30/tree/master/18_Adding-Up-Times-with-Reduce)
