---
description: 리액트의 상태가 불변해야하는 이유는?
---

# State Immutability

<figure><img src="../../.gitbook/assets/Call_by_value_and_call_by_reference (1).png" alt=""><figcaption><p>Call by value vs call by reference <a href="https://press.rebus.community/programmingfundamentals/chapter/call-by-value-vs-call-by-reference/">1)</a></p></figcaption></figure>

| Primitive Type                                         | Object Type                                                                         |
| ------------------------------------------------------ | ----------------------------------------------------------------------------------- |
| Call by Value                                          | Call by Reference                                                                   |
| <ul><li>호출되면 값을 복사해서 사용</li><li>사용되는 메모리 늘어남</li></ul> | <ul><li>호출되면 직접 참조해서 사용</li><li>직접 참조하기 때문에 원본이 변경 가능하기 때문에 모든 참조가 영향을 받음</li></ul> |

자바스크립트는 객체이기 때문에 무엇이 변경되었는지 알기 어려울 수 있다.

리액트는 shallow compare를 하기 때문에 참조 주소가 변경되었는지만 확인해서 변경되었다고 파악한다.

그렇기에 Object의 경우 내부 값이 변경되었다고 해도 참조 주소는 변경되지 않기 때문에 변경되었는지 여부를 파악할 수 없다.



