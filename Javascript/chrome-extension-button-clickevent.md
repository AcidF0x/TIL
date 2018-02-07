# 크롬 확장프로그램 - Background에서 클릭 감지
## 내용

크롬 확장플러그인 아이콘을 클릭하시는경우 기능을 ON/OFF 하려는 하였으나  
아이콘을 클릭하는 경우 후 로직을 실행 한뒤 `window.close()` 을 사용 하여 창을 닫는 방법으로 구현하였지만  
로직이 비동기로 실행 되므로 일정 시간동안 popup의 Bubble이 표시되었음

```javascript
//manifest.json
  "browser_action": {
    'default_popup' : "popup.html"
  }
```
```html
//popup.html
    <html>
    <body>
    <script src="js/popup.js"></script>
    </body>
    </html>
```
```javascript
//popup.js

window.onload = function () {
    //doSomeThing();
    //window.close();
}
```
## 해결

해당 기능을 popup이 아닌 background에서 `chrome.browserAction.onClicked` 이벤트에 리스너를 추가하여 기능을 구현함

```javascript
//manifest.json
// "browser_action": {
// 'default_popup' : "popup.html"
// }
```
```javascript
//background js

chrome.browserAction.onClicked.addListener(function(e){
    //doSomeThing();
});

```

## 참고 문서

- [Chrome browserAction Event](https://developer.chrome.com/extensions/browserAction#event-onClicked)