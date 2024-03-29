# Implement experiences



Front-end Stack: React, Next.js, react-query, formik, zustand

Development Environment: Node.js, MongoDB, github Actions, docker, AWS



## Props Drilling

<div align="left">

<figure><img src="../.gitbook/assets/스크린샷 2024-02-01 오후 11.19.33.png" alt="" width="375"><figcaption><p>Structure of Chat</p></figcaption></figure>

</div>

채팅 안에 견적서를 생성하는 기능을 추가하면서 기존 채팅 컴포넌트 내에서 발생하고 있던 props drilling을 가중시키게 되어 해당 기능 개발 후 리팩토링을 진행하게 되었다.

Props drilling은 컴포넌트 네스팅으로 인해 하위 컴포넌트에게 전달되어야 하는 props를 모두 부모 컴포넌트에서 부터 전달해야하기 때문에 하위 컴포넌트들은 해당 컴포넌트와 상관없는 props까지 전달하게 되면서 복잡성을 크게 야기시킨다. 이를 해결하기 위해 기존에 사용하고 있던 Zustand를 이용했다.&#x20;

Zustand는 상태 관리 라이브러리로 Context API와 가장 큰 차이점은 메모이제이션을 통해 값을 반환하기 때문에 참조가 변경이 될때만 리랜더링을 발생시켜 랜더링 최적화에 큰 장점이 있다.



## 기술부채

모노레포로 발생하는 컴포넌트 의존 관계 분리 작업 진행했다.

모노레포는 하나의 레파지토리 안에 다양한 서비스(프로젝트)를 관리하는 방법을 의미한다. 모노레포로 구성된 이유를 추측해보면 짧은 시간 안에 두 개의 어플리케이션을 개발해야했고 이 두 개의 어플리케이션은 비슷한 기능과 디자인을 공유하는 것이 많아 즉, 재사용 할 수 있는 컴포넌트가 많았기 때문에 효율적으로 빠르게 개발할 수 있는 모노레포를 채택한 것으로 보인다. 하지만 계속 전역 컴포넌트(공통 컴포넌트)와 지역 컴포넌트(어플리케이션 내에서만 사용하는 컴포넌트) 간의 의존 관계가 얽히고 복잡해지면서 기술 부채로 남게 되었다. 이를 해결하기 위해서 사용하던 모든 컴포넌트를 조사하고 의존 관계를 파악하여 리팩토링하는 시간을 가졌다.

단점으로 볼 수 있는 것은 전역 컴포넌트의 경우 수정하게 되면 사용하고 있는 모든 어플리케이션에 영향을 미치기 때문에 이런 부분을 잘 확인해야하며, 어플리케이션에 따라 분기처리가 많아서 코드의 복잡성이 높아지는 문제를 경험했다.

고객 사이드와 어드민 사이드로 두 개의 어플리케이션이 있고 고객 사이드에는 두명의 타겟, 어드민에 한명의 타겟으로 총 세명의 타겟을 위한 디자인과 기능이 제공되어야 했다. 이를 하나의 공통 컴포넌트에서 처리하다 보니 기능과 디자인 모두 분기가 필요한 경우가 많아 상당히 복잡하여 유지보수 측면에서 시간 소요가 많이 되었다.
