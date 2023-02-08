# 속성 attribute

```javascript
const id = document.getElementById("id");
const isValid = id.hasAttribute("title"); //boolean; titile이란 속성이 설정되어 있는가?
//content 속성으로 작성했는가 안했는가가 기준 <label title="title" />

const attributes = id.attributes;
const isValidAttributes = id.hasAttributes(); //속성이 있는지 없는지 boolean
console.log(attributes.item(1).nodeName); // [1]번째 속성의 값이 출력
```

프로퍼티 원래 있는 속성 el.title vs el\["font-size"] 프로퍼티 키로 접근 IDL

커스텀인 경우에는 getAttribute로 하는 것이 좋음? content



```javascript
const el = document.getElementById("id");
const list = el.getAttributeNames(); //array로 모든 속성 내용이 담겨 나옴

const node = el.getAttributeNode("title"); //속성을 Attr객체로 반환함
```

sequence 란?

<<"a", "b">> 값을 각 콤마로 구분 Infra?

```javascript
//뭔가 만드는c는 document에서 나머지 rud는 Element 인터페이스에서

const created = document.createAttribute("isActive");
created.value = true;

const new = document.getElementById("id"); //(name, value)
new.setAttribute(created); //만든 속성을 엘리먼트에 적용 

new.ownerElement.id; //??

new.setAttributeNode(created); //????? 설정 결과과 필요할 때 이걸 사용하자?

```



Attr 인터페이스

```javascript
new.removeAttribtue("id"); //삭제된 것을 반환하지 않음

const attr = el.getAttributeNode("category");
new.removeAttributeNode(attr); //오브젝트 attr 형태로 파라미터에 전달 삭제된 attr 객체로 반환


const result = el.toggleAttribute("id"); //결과는 boolean
el.ontoggle = () => {};
el.open //open 프로퍼티
```
