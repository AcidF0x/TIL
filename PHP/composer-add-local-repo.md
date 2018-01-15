# 패키지 작업중 로컬 저장소 사용
## 상황설명
라라벨 패키지 [Laravel-EzThrottle](https://github.com/AcidF0x/Laravel-EzThrottle) 개발중  
실제 작동하는 지 확인하기 위해 라라벨 프로젝트에 해당 패키지를 설치 하기 위한 목적으로   
컴포저에 해당 프로젝트의 위치를 임의로 입력
 

```bash 
#composer.php

"require": {
    "{패키지명}" : "dev-master"
},
"repositories": [
        {
            "type": "path",
            "url": "{패키지 경로}"
        }
    ]
```

## 기타
해당 패키지를 vendor폴더에 다운로드 하는 것이 아닌 심볼릭 링크를 거는 방식  
내용이 변경되더라도 심볼릭 링크이므로 문제가 발생하지 않음

