## Custom Video Player

實作一個客製化的影片播放器。

## Snippets

```js
function togglePlay() {
	const method = video.paused ? 'play' : 'pause';
	video[method]();
}
```

影片是否在撥放可以藉由 `video.paused` 來判定，並驅動 `play()` 或 `video[play]` 及 `pause()` 和 `video[pause]` 的方式操控影片。

```js
function handleRangeUpdate() {
	video[this.name] = this.value;
}

ranges.forEach(range => range.addEventListener('change', handleRangeUpdate));
ranges.forEach(range => range.addEventListener('mousemove', handleRangeUpdate));
```

利用 `change` 或 `mouseover` 控制，選取 `this.name` 並給 `this.value` 的值。

`video[volumn]` 及 `video[playbackRate]` 分別設定聲音及撥放速度。

```js
function handleProgress() {
	const percent = (video.currentTime / video.duration) * 100;
	progressBar.style.flexBasis = `${percent}%`;
}
```

利用 `video.currentTime` 取當前值，除以 `video.duration` （全長）並乘上 100 得知進度條的比例位置。

控制 CSS 的呈現，設定 `progressBar.style.flexBasis = ${percent}%`。

```js
function scrub(e) {
	const scrubTime = (e.offsetX / progress.offsetWidth) * video.duration;
	video.currentTime = scrubTime;
}

let mousedown = false;
progress.addEventListener('click', scrub);
progress.addEventListener('mousemove', (e) => mousedown && scrub(e));
progress.addEventListener('mousedown', () => mousedown = true);
progress.addEventListener('mouseup', () => mousedown = false);
```

傳遞事件值，用 `e.offsetX` 取得在當下該 div 的 x 值，除以全長 `progress.offsetWidth` 得到百分比，乘 `video.duration` 可知目前的撥放時間，並放到 `video.currentTime`。

設定 `mousedown = false` 為 flag，按下 `mousedown` 為 `true`，放開時 `mouseup` 為`false`，移動時 `mouseover` 判定 `mousedown` 參數為 `true` 時執行事件。

## References

- [dwatow](https://github.com/dwatow/JavaScript30/tree/master/11%20Custom%20Video%20Player)
- [dustinhsiao21](https://github.com/dustinhsiao21/Javascript30-dustin/tree/master/11%20-%20Custom%20Video%20Player)
- [guahsu](https://github.com/guahsu/JavaScript30/tree/master/11_Custom-Video-Player)
- [a90100](https://github.com/a90100/JavaScript30/tree/master/11%20-%20Custom%20Video%20Player)
