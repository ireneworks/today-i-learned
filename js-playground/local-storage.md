# 로컬스토리지 Local Storage

JSON key, value로 저장

무조건 문자열로 저장됨

브라우저 안에 저장되는 데이터들을 모아놓은 공간 중 하나

HTTP 요청에서 데이터를 주고 받지 않아도 데이터가 로컬 디스크에서 꺼내 사용

인터넷이 끊어져도 데이터가 삭제되거나 지워지지 않음

최대 용량 5MB



```
localStorage.setItem("key", value)
localStorage.getItem("key")
localStorage.removeItem("key")
localStorage.clear()
localStorage.length //키, 값 쌍 개수
```
