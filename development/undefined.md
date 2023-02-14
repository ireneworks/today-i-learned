# 개발 Implementation

<figure><img src="../.gitbook/assets/스크린샷 2023-02-14 오후 1.45.46.png" alt=""><figcaption><p>CS 50 2019 Computational Thinking, Scratch <a href="https://www.youtube.com/watch?v=jjqgP9dpD1k&#x26;list=PLhQjrBD2T381L3iZyDTxRwOBuUt6m1FnW">1)</a></p></figcaption></figure>

개발에서 문제 해결이란, 데이터를 받아서 input 처리하고 결과를 출력 output 하는 것을 의미한다. 박스 안에 들어갈 처리 방법을 고민하는 것이 목표이다.

* 해결해야할 문제(Acceptance criteria)를 정의하고 문제 해결 방안을 도출한다.
* 해결 과제를 작은 단위로 분해하고 패턴화해서 평가가 가능하도록 정의해야 한다.



### 시맨틱 Semantic

코드 뿐만 아니라 코드 그룹에 흐름을 쉽게 이해할 수 있도록 앞뒤로 연결지어 시맨틱하게 작성하자

```javascript
//함수 이름에 시맨틱을 부여하면 함수 블록의 코드를 읽지 않아도 함수 기능을 짐작 가능
//이름만 봐도 값을 리턴하겠구나

const values = [1, 2];
const getValue =  (index) => {
    return values[index]
};
const value = getValue(1);
console.log(value); // 2
```

```
Semantic + Nuance 

모자를 쓰다 vs 글을 쓰다 //쓰다라는 단어는 같지만, 행동이 아예 다름

//시멘틱 뿐만 아니라 뉘앙스(목적)까지 제한해서 단순화하자 -> 원하는 것이 무엇인지 정리하자
```

