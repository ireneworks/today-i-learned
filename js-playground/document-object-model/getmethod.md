# getMethod

mixin은 인스턴스가 없기 때문에 하나의 인터페이스에 속해있어야 사용할 수 있고, 하나인 경우 partial, 다양한 곳에서 사용할 수 있다면 mixin



```javascript
//id로 DOM을 찾음

const id = document.getElementById("id"); // 가장 가까운 엘리먼트를 객체로 반환
```

```javascript
//모든 엘리먼트 반환

const el = document.getElementsByClassName("category"); //category를 포함하는 모든 엘리먼트를 객체로 반환
```

```javascript
//document vs element

const el = document.getElementsByTagName("span"); //document인 경우 전체 도큐먼트에서 검색해 반환
el.getElementsByTagName("button"); //element인 경우 서브트리


//namespace란 "http://naver.com" 같은 것??

const el = document.getElementsByTagNameNS(namespace, "div") //???? namespace를 주지 않으면 디폴트 값이 설정됨
```
