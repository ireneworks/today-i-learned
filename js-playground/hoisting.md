# 호이스팅 Hoisting

인터프리터가 변수와 함수의 메모리 공간을 선언 전에 미리 할당해서 효율적으로 관리하기 위함이다.

→ 변수/함수 선언문을 유효범위의 최상단으로 끌어올리는 것



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

1. TDZ(Temporarily Danger Zone)
2. 선언 단계
3. 초기화 및 할당 단계:&#x20;

| 스코프  | 재할당       |
| ---- | --------- |
| 코드블록 | X (const) |

```javascript
console.log(x); //Reference Error TDZ
const x = 1;
console.log(x); // 1
```
