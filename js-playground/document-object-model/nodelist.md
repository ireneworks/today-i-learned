# NodeList

```javascript
// nodeList는 이터러블 객체

const el = document.querySelectorAll("category");
const index = el.item(0); // [0] 인덱스 엘리먼트를 반환
const keep = el.forEach(el => console.log(el.textContext)); // category인 노드리스트를 콘솔에 찍음
```
