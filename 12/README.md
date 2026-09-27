## Key Sequence Detection

做一個輸入按鍵（Key Sequence）就會顯示特殊畫面的網頁。

## Snippets

```js
pressed.splice(-secretCode.length - 1, pressed.length - secretCode.length);
```

透過運算使 pressed 陣列長度始終與密碼相同，且超出時替換掉陣列第一個元素。

`splice(start, deleteCount, item1, item2, ...)` 可以對陣列內容進行刪除或新增。

第一個參數為開始位置，若為負值則會反著數（由陣列尾部開始）。

第二個參數為移除數量，若為 0 則不移除、負值則沒反應。

第三個參數為加入元素，可從第一個參數位置開始塞陣列元素。

## References

- [dustinhsiao21](https://github.com/dustinhsiao21/Javascript30-dustin/tree/master/12%20-%20Key%20Sequence%20Detection)
- [guahsu](https://github.com/guahsu/JavaScript30/tree/master/12_Key-Sequence-Detection)
