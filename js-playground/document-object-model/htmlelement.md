# HTMLElement

```javascript
innerText //script, style 내용은 노출되지 않음
outerText

console.log(el.innerText); //공백은 나오지 않고 텍스트 노드는 같이 나옴
console.log(el.outerText); //텍스트 반환은 innerText랑 동일하지만 값을 설정하면 자신과 서브트리까지 포함해 해당 텍스트로 대체함
```

```javascript
innerHTML mixin HTML parsing
outerHTML partial

console.log(el.innerHTML); // < > & 이런 기호들 다 인코딩 되어서 노출 
//<p id="id">&lt;실내&gt;</p>

console.log(el.outerHTML); //
```

```javascript
el.insertAdjacentHTML("position", text); //#basis 기준 파싱해서 삽입

afterbegin //기준 엘리먼트 바로 다음
beforeend //마지막 child 엘리먼트에
beforebegin //바로 앞에 형제 엘리먼트
afterend //basis 서브트리가 끝나고 난 후 다음 sibiling 엘리먼트

```
