# live, static

live -> document에 element를 추가/삭제 했을 때 바로 반영됨

static -> 바로 반영되지 않음



```javascript
const buttons = document.getElementById("buttons")
const sports = document.querySelectorAll("sports")


const onClickHandler = () => {
    const el = document.createElement("li");
    el.textContext = "버튼";
    buttons.appendChild(el);
    sports.appendChild(el); //nodeList는 바로 반영되지 않음
}

buttons.onClick = onClickHandler; //buttons를 클릭하면 마지막 child에 생김

//노드 트리에 노드(엘리먼트)를 추가/삭제하면 HTMLCollection에 추가되고 바로 반영됨



```

