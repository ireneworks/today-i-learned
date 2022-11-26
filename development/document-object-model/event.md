# Event

```javascript
// 이벤트 추가

const el = document.getElementById("one");
const show = () => {
    console.log("이벤트 ->", "눌렸다")
}

el.addEventListner("click", show, false); //true는 캡쳐, false는 버블

el.removeEventListner("click", show, false); //동일한 조건의 이벤트만 삭제됨

el.onClick = show; //HTML eventHandler는 on+이름 IDL 형태 옵션 캡쳐나 버블 사용할 수 없음
el.onClick = null; //null을 설정하는건 삭제하는거랑 똑같음

<p id="one" onClick="show()">하나</p> //content 속성으로 이벤트 핸들러 작성 가능
```



DOM은 eventListner

HTML은 eventHandler (onClick과 같은 이름)

