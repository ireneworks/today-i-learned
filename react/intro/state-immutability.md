---
description: 리액트의 상태가 불변해야하는 이유는?
---

# State Immutability

<figure><img src="../../.gitbook/assets/Call_by_value_and_call_by_reference (1).png" alt=""><figcaption><p>Call by value vs call by reference <a href="https://press.rebus.community/programmingfundamentals/chapter/call-by-value-vs-call-by-reference/">1)</a></p></figcaption></figure>

| Primitive Type                                         | Object Type                                                                        |
| ------------------------------------------------------ | ---------------------------------------------------------------------------------- |
| Call by Value                                          | Call by Reference                                                                  |
| <ul><li>호출되면 값을 복사해서 사용</li><li>사용되는 메모리 늘어남</li></ul> | <ul><li>호출되면 직접 참조해서 사용</li><li>직접 참조하기 때문에 원본이 변경 가능, 때문에 모든 참조가 영향을 받음</li></ul> |

리액트는 상태가 변경되어야 랜더링 할 수 있기 때문에 무엇이 달라졌는지 파악할 수 있어야한다.

리액트는 얉은 비교 shallow compare를 한다.

불변성이라하면 메모리에 저장된 값은 변하지 않는 것을 이야기한다. 비교할 이전 상태가 변경되지 않아야 새로운 상태와 비교할 수 있기 때문에..?

원시 타입은 값으로 비교가 가능한 이유가 참조하고 있는 메모리의 값을 변경하는 것이 아닌 새로운 메모리에 값을 넣어서 참조 주소가 변경되기 때문에 이전 값이 변경되지 않아 비교가 가능하다.

다만, Object 타입은 내부 값이 변경되어도 참조하고 있는 객체의 참조 주소가 변경되지 않기 때문에 변경 여부를 파악할 수 없다. Object.is 로 비교한다.

그래서 객체인 경우 기존 state에 변경을 해도 변경됨을 알 수 없기 때문에 새로운 객체로 만들어 전달해야하며 대체로 많이 쓰이는 방법이 spread 연산자이다.



