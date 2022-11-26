# Element

Element 인터페이스는 속성 attribute를 설정하는 기능 집합이네



### XML이란

Extensible Markup Language

JSON(텍스트) 나오기 전에는 XML(객체)많이 이용했음



커스텀 태그를 이용할 수 있음

커스텀 태그가 겹칠 수 있기 때문에 네임스페이스가 필요했나보다 (prefix가 다르면 다른 엘리먼트로 인식함)

태그네임은 prefix:localName 전체를 보여줌

속성도 prefix:속성이름="value"



## IDL vs content 속성

### IDL이란

Interface Definition Language

자바스크립트의 프로터피도 바인딩된 형태



```javascript
//content 속성

const el = document.getElementById("category"); 
const value = el.getAttribute("tabindex"); //설정된 속성인 tabindex 값을 담음
el.setAttribute("name", "nickname");
```

```javascript
//IDL 속성

const el = document.getElementById("category");
el.tabIndex = 77; // 자바스크립트 형태로 이름이 변경됨,  key: value 형태로 프로퍼티가 바인딩됨 ??
 // 카멜케이스
```
