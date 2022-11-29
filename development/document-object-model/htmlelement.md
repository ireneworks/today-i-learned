# HTMLElement

```javascript
innerText //script, style 내용은 노출되지 않음
outerText

console.log(el.innerText); //공백은 나오지 않고 텍스트 노드는 같이 나옴
console.log(el.outerText); //텍스트 반환은 innerText랑 동일하지만 값을 설정하면 자신과 서브트리까지 포함해 해당 텍스트로 대체함
```

```javascript
innerHTML mixin HTML parsing함
outerHTML partial

console.log(el.innerHTML); // < > & 이런 기호들 다 인코딩 되어서 노출 
//<p id="id">&lt;실내&gt;</p>
```
