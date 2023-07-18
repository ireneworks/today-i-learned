# Props and State

component 즉 Element는 pure function이기 때문에 값이 수정되지 않는다. 즉, 외부에 영향을 주지 않은 부수효과가 없는 함수라서

```javascript
// pure function이 아닌 이유는 외부에 영향을 주기 때문에 이는 부수효과라 함

const obj = {key: 1}

function change (value: number) {
    obj.key = value
}

// pure function은 외부에 영향을 주지 않고 주어진 값으로 계산하여 예상되는 결과 값을 제공

function add (a:number, b:number):number {
    return a + b;
}
```



그래서 state가 비동기적으로 실행되는 이유도 랜더링이 완료된 후에 값을 갱신함으로써 불필요한 랜더링을 방지하며 react element는 immutable하기 때문에 element가 생성된 후에는 children, props를 수정할 수 없다.

