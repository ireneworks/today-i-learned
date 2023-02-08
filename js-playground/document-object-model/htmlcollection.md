# HTMLCollection

ElementCollection

NodeCollection

리스트로 되어 있음

```javascript
//엘리먼트를 인덱스로 구할 수 있음

const el = document.getElementsByClassName("category");
const index = el.item(1); //클래스로 추출한 엘리먼트 중에서 [1]에 있는 엘리먼트를 반환
```

```javascript
//엘리먼트를 네임속성으로 구할 수 있음

const el = document.getElementsByClassName("category");
const find = el.namedId("fiction"); //fiction인 id, name, class 등의 속성 값과 일치하는 첫번째 엘리먼트 반환
```

for in 인지 for of 인지 구분해야함

ArrayLike 여서 다를 수 있데

