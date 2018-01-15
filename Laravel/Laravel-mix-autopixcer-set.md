# Laravel-Mix autoprefixcer 브라우저 설정

라라벨에서 제공하는 프론트엔드 컴파일러 `laravel-mix`를 이용하여 css를 컴파일 하는경우  
기본적으로 `autoprefixer`가 작동하여 css의 `vendor-prefix`를 자동으로 설정해줌   
허나 브라우저의 지원 범위를 설정하기 위해 `webpack.config`를 수정 하였으나 반영이 안됨  
`package.json`파일에 지원 범위를 적어 주면 정상적으로 반영이 됨  
해당 옵션은 [링크](https://github.com/ai/browserslist#queries)참고

```bash 
#package.json

  "browserslist": [
    "last 3 versions",
    "ie 9"
  ]
  
```


