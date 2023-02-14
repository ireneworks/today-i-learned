# 노드 Node

```javascript
<div id="category"> 카테고리 <strong> 도구리 </strong> 좋아요 </div>

const el = document.getElementById("category");
const text = el.textContext;  // 서브트리가 있어도  그 내용까지 다 노출
console.log(text); //카테고리 도구리 좋아요
```

노드 트리

노드 구조는 부모는 하나여야 한다

1:1 관계

parentNode, childNodes

구조가 아닌 관계

노드 관계의 포지션

부모 위치에 있는 노드를 가져온다

relative 같은 느낌?

first child

last child

previos sibling

next sibling

