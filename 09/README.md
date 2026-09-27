## Dev Tools Domination

介紹幾個 `Dev Tools` 和 JS 除錯的方式。

## Snippets

`console.log('hello %s', 'world')` 可以用替代字符。

`console.log('%c hello world', 'font-size: 50px')` 加入 CSS 樣式。

`console.assert()` 若第一參數為 `false` ，則會輸出第二參數內容。

`console.dir()` 查看被選取的 DOM 元素屬性。

```js
dogs.forEach(dog => {
	console.groupCollapsed(`${dog.name}`);
	console.log(`This is ${dog.name}`);
	console.log(`${dog.name} is ${dog.age} years old`);
	console.log(`${dog.name} is ${dog.age * 7} dog years old`);
	console.groupEnd(`${dog.name}`);
});
```

`group` 資料。

`console.count()` 計算參數出現的次數。

```js
console.time('fetching data');
fetch('https://api.github.com/user/wesbos')
	.then(data => data.json())
	.then(data => {
		console.timeEnd('fetching data');
		console.log(data);
});
```

`console.time()` 計算 `time` 到 `timeEnd` 的執行時間。

## References

- [dwatow](https://github.com/dwatow/JavaScript30/tree/master/09%20Dev%20Tools%20Domination)
- [dustinhsiao21](https://github.com/dustinhsiao21/Javascript30-dustin/tree/master/09%20-%20Dev%20Tools%20Domination)
- [guahsu](https://github.com/guahsu/JavaScript30/tree/master/09_Dev-Tools-Domination)
- [a90100](https://github.com/a90100/JavaScript30/tree/master/09%20-%20Dev%20Tools%20Domination)
