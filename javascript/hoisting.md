# 호이스팅 Hoisting

인터프리터가 변수와 함수의 메모리 공간을 할당 전에 미리 메모리에 할당해서 효율적으로 관리하기 위함이다.

변수가 선언이 되고 이후 var의 경우 선언과 초기화가 동시에 일어나기 때문에 메모리에 undefined로 초기화가 되고 이후 변수에 할당문이 있는 코드에서 값이 할당된다. 그렇기 때문에 할당문 전에 var 변수를 참조해도 에러가 아닌 undefined로 값이 나온다. 반면 let, const는 선언과 초기화/할당이 분리되어 있기 때문에 선언은 되어있지만 초기화/할당이 되지 않았기 때문에 참조하면 reference error/초기화 에러가 난다. TDZ 스코프는 이렇게 선언은 되었으나 초기화되지 않은 스코프에서 참조하는 것을 금지하고 있다.



### var

1. 선언 단계: 변수를 실행 컨텍스트의 변수 객체에 등록 `var name`
2. 초기화 단계: 실행 컨텍스트에 등록된 변수 객체에 대한 메모리 할당 (변수는 undefined로 초기화)&#x20;
3. 할당 단계: undefined로 초기화된 변수에 값 할당 `var name = "mochi";`

```javascript
console.log(num); //호이스팅한 var num 선언해서 undefined
var num; //호이스팅 선언&초기화
num = 6; //할당
```

| 스코프 | 재할당          | 재선언 |
| --- | ------------ | --- |
| 함수  | O (var, let) | O   |

###

### let, const

1. 선언 단계
2. TDZ(Temporarily Danger Zone)
3. 초기화 및 할당 단계

| 스코프  | 재할당       |
| ---- | --------- |
| 코드블록 | X (const) |

```javascript
console.log(x); //Reference Error
const x = 1;
console.log(x); // 1
```
