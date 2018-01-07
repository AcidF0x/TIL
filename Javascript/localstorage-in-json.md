# LocalStorage에 JSON저장하기
## 문제

LocalStorage에 JSON 을 저장하는경우 문제가 발생함  

```javascript
var MyNameIsJSON = { 
    id : 1,
    text : "I am JSON Data!!"
};

localStorage.setItem('jsonData', MyNameIsJSON);
```

![imgur](https://i.imgur.com/UqQYzxJ.png)


## 해결

JSON을 `JSON.stringify()` 로 처리후 저장한다.  

```javascript

var MyNameIsJSON = { 
    id : 1,
    text : "I am JSON Data!!"
};

localStorage.setItem('jsonData', JSON.stringify(MyNameIsJSON));
```

## 기타
생각해보면 당연한 문제였다  
localStorage는 단순한 text Key / Value 스토리지 이므로 처리가 필요했다  
역으로 불러올때도 역시 당연 처리를 해준다  

```
var myJson = JSON.parse(localStorage.getItem('jsonData'));
```

## 참고 문서

- [MDN - localStorage](https://developer.mozilla.org/ko/docs/Web/API/Window/localStorage)