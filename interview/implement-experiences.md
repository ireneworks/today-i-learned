# Implement experiences



Front-end Stack: React, Next.js, react-query, formik, zustand

Development Environment: Node.js, MongoDB, github Actions, docker, AWS



## Props Drilling

<div align="left">

<figure><img src="../.gitbook/assets/스크린샷 2024-02-01 오후 11.19.33.png" alt="" width="375"><figcaption><p>Structure of Chat</p></figcaption></figure>

</div>

채팅 안에 견적서를 생성하는 기능을 추가하면서 기존 채팅 컴포넌트 내에서 발생하고 있던 props drilling을 가중시키게 되어 해당 기능 개발 후 리팩토링을 진행하게 되었다.

Props drilling은 컴포넌트 네스팅으로 인해 하위 컴포넌트에게 전달되어야 하는 props를 모두 부모 컴포넌트에서 부터 전달해야하기 때문에 하위 컴포넌트들은 해당 컴포넌트와 상관없는 props까지 전달하게 되면서 복잡성을 크게 야기시킨다. 이를 해결하기 위해 기존에 사용하고 있던 Zustand를 이용했다. 견적서 생성 컴포넌트에서 필요한 props와 채팅에서 필요한 props를 분리하여 store를 만들어 제공했다.

Zustand는 상태 관리 라이브러리로 Context API와 가장 큰 차이점은 메모이제이션을 통해 값을 반환하기 때문에 참조가 변경이 될때만 리랜더링을 발생시켜 랜더링 최적화에 큰 장점이 있다.



## 기술부채

모노레포로 발생하는 컴포넌트 의존 관계 분리 작업 진행
