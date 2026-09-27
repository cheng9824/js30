## JavaScript Reference VS Copying

了解 JS 的 Copy 和 Reference 之間的差異。

## Snippets

```js
const players = ['Wes', 'Sarah', 'Ryan', 'Poppy'];

const team = players;
const team2 = players.slice();
const team3 = [].concat(players);
const team4 = [...players];
const team5 = Array.from(players);
```

陣列的淺複製，新陣列內容被修改時，原陣列也會被修改。

```js
const person = {
	name: 'Wes Bos',
	age: 80
};

const cap2 = Object.assign({}, person, { number: 90, age: 15 });
```

物件的淺複製，新物件內容被修改時，原物件內容也會被修改。

```js
const wes = {
	name: 'Wes',
	age: 100,
	social: {
		twitter: '@wesbos',
		facebook: 'wesbos.developer'
	}
}

const dev2 = JSON.parse(JSON.stringify(wes));
```

若要完全（深）複製的話，可以用以上的方式處理。

## References

- [dwatow](https://github.com/dwatow/JavaScript30/tree/master/14%20JavaScript%20References%20VS%20Copying)
- [dustinhsiao21](https://github.com/dustinhsiao21/Javascript30-dustin/tree/master/14%20-%20JavaScript%20References%20VS%20Copying)
- [guahsu](https://github.com/guahsu/JavaScript30/tree/master/14_JavaScript-References-VS-Copying)
- [a90100](https://github.com/a90100/JavaScript30/tree/master/14%20-%20JavaScript%20References%20VS%20Copying)
