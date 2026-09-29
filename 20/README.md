## Speech Detection

介紹與使用瀏覽器內建語音轉文字的 web speech api。

## Snippets

```js
window.SpeechRecognition =
  window.SpeechRecognition || window.webkitSpeechRecognition;

const recognition = new SpeechRecognition();
recognition.interimResults = true;
```

建立 SpeechRecognition。

```js
let p = document.createElement("p");
const words = document.querySelector(".words");
words.appendChild(p);
```

設定輸出。

```js
recognition.addEventListener("result", (e) => {
  console.log(e);
  const transcript = Array.from(e.results)
    .map((result) => result[0])
    .map((result) => result.transcript)
    .join("");

  p.textContent = transcript;
  if (e.result[0].isFinal) {
    p = document.createElement("p");
    words.appendChild(p);
  }
});

recognition.addEventListener("end", recognition.start);

recognition.start();
```

監聽視別系統。

## References

- [dustinhsiao21](https://github.com/dustinhsiao21/Javascript30-dustin/tree/master/20%20-%20Speech%20Detection)
- [guahsu](https://github.com/guahsu/JavaScript30/tree/master/20_Speech-Detection)
