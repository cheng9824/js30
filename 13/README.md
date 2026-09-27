## Slid in on Scroll

製作圖片移入、移出的效果，當視窗移到對應區域以勪畫方式出現。

## Snippets

```js
function debounce(func, wait = 20, immediate = true) {
	var timeout;
	return function () {
		var context = this, args = arguments;
		var later = function () {
			timeout = null;
			if (!immediate) func.apply(context, args);
			};
		var callNow = immediate && !timeout;
		clearTimeout(timeout);
		timeout = setTimeout(later, wait);
		if (callNow) func.apply(context, args);
	};
}

window.addEventListener('scroll', debounce(checkSlide));
```

使滾動視窗到定點時顯示效果，用 `window` 監聽整個視窗，事件選用 `scroll`，  
但若使用 `scroll` 來操作，則每次的畫面滾動都會有大量事件觸發，對效能上造成影響，所以多寫了一個 `debounce` 來使觸發間隔為 20 毫秒以上。

```js
function checkSlide(e) {
	console.log(window.scrollY);
	sliderImages.forEach(sliderImages => {
		const slideInAt = (window.scrollY + window.innerHeight) - sliderImages.height / 2;
		const imageBottom = sliderImages.offsetTop + sliderImages.height;
		const isHalfShown = slideInAt > sliderImages.offsetTop;
		const isNotScrolledPast = window.scrollY < imageBottom;
		if (isHalfShown && isNotScrolledPast) {
			sliderImages.classList.add('active');
		} else {
			sliderImages.classList.remove('active');
		}
	});
}
```

先取得圖片 1 / 2 高度的定位點（卷軸垂直位移量 ＋ 視窗高度）- 1 / 2 圖片高度，再取得圖片底部定位點（利用圖片頂部定位點 + 圖片高度取得）。

接著判斷視窗是否已經超過圖片高度一半，和滾動範圍是否已經超過圖片底部（卷軸垂直位移量），及是否超過圖片一半高，且視窗尚未超過圖片底部來增加或移除 css 效果。

## References

- [dwatow](https://github.com/dwatow/JavaScript30/tree/master/13%20Slide%20in%20on%20Scroll)
- [dustinhsiao21](https://github.com/dustinhsiao21/Javascript30-dustin/tree/master/13%20-%20Slide%20in%20on%20Scroll)
- [guahsu](https://github.com/guahsu/JavaScript30/tree/master/13_Slide-in-on-Scroll)
