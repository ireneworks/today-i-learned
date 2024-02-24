# 면접 Interview

### 리액트를 왜 사용할까?

페이스북이 리액트를 개발하게 된 이유는 고객과의 많은 인터렉션으로 인해 실시간으로 변경되는 데이터를 바인딩하여 화면을 안정적으로 고객에게 제공하기 위함이다. 즉, 사용자 인터페이스에 초점을 맞추어 라이브러리를 만들었다.

바닐라 자바스크립의 경우 직접 DOM을 조작하여 화면을 랜더링 했다. DOM을 직접 조작하는 것은 문제되지 않지만 화면에서 많은 변화가 필요한 어플리케이션의 경우 필요한 부분을 하나하나 DOM을 조작하여 랜더링하게 된다면 reflow, repaint의 과정을 반복하여 연산이 잦아지면서 성능에 영향을 줄 수 있다. 이를 해결하기 위해서 리액트에서는 변경이 필요한 부분을 모아 랜더링을 시키고자 한다.



### 브라우저 랜더링

TBU



### Virtual DOM

가상 돔(Virtual DOM)은 Real DOM에 반영되어야하는 사항들을 한번에 모아서 적용하기 위해 사용하고 있다.&#x20;

가상 돔은 DOM 트리가 객체로 되어있다. 가상 돔이 객체인 이유는 자바스크립트가 쉽게 접근(탐색)하고 변경할 수 있는 자료구조이기 때문이다.

#### 생성 Render

<figure><img src="../.gitbook/assets/image.png" alt=""><figcaption><p>React Fiber <a href="https://velog.io/@jangws/React-Fiber">1)</a></p></figcaption></figure>

```jsx
// JSX가 아닌 직접 리액트 엘리먼트를 만든다면
React.createElement(type, property, childrenNode)

<h1 id='title'>Hello World</h1>
React.createElement('h1', {id: 'title'}, 'Hello World')
```

```jsx
// 리액트 엘리먼트를 까본다면
{
    $$typeof: Symbol(React.element),
    'type': 'h1',
    'key': null,
    'ref': null,
    'props': {'id': 'title', 'children': [
        {'type': 'h2', 'props': {'children': 'subTitle'} ...},
        {'type': 'h2', 'props': {'children': 'subTitle'} ...},
        ...
    ]},
    '_owner': null,
    '_store': {}
}
```

리액트의 diff란 이전 버전의 가상 돔과 최신 버전의 가상 돔을 비교한다. DFS 알고리즘으로 비교하면서 Real DOM 업데이트가 필요한 노드가 있다면 flag를 달아둔다.



**비교**

컴포넌트 코드를 한줄 한줄 읽으면서 최신 가상 돔 객체(props, style 등이 포함)로 만든다. 각 컴포넌트에 useEffect와 같은 Effect(Hooks)가 있다면 따로 수집하여 Effect list를 만들고 이는 commit phase 이후에 모두 화면에 랜더링이 완료된 후에 실행한다.

\*이때 함수 컴포넌트에서 props를 다룰 때 순수 함수처럼 동작해야한다. props는 읽기 전용으로 만약 부수효과가 있으면 상위 부모 가상 돔 객체가 변경될 가능성이 있고 결국 한번에 비교를 하는 것이 아닌 여러번 비교를 해야하는 문제가 발생할 수 있다. 때문에 props는 immutable 해야하며 생성된 후에는 수정할 수 없다.

먼저 엘리먼트의 타입을 비교한다. 타입이 다르다면 새로운 트리 즉, 객체를 생성한다.

타입은 같으나 속성이 다르다면 변경이 필요한 속성만 업데이트 한다.

자식 노드가 변경된다면 key로 비교하여 변경한다. 가장 비효율적인 방법은 전체 DOM을 지우고 재구성하는 것이다. 왜냐하면 엘리먼트를 DOM에 삽입하는 것이 가장 비싼 연산이기 때문이다. 그래서 이를 최소화하기 위해서 key 값을 통해 변경이 필요한 부분을 찾고 해당 DOM만 수정한다.

\*key 값으로 인덱스를 사용하게 된다면 비효율적일 수 있다. key는 동일하나 요소가 변경된다면 결국 변경되었다고 리액트가 판단하여 새로운 DOM 트리를 생성하게 된다.

```jsx
// 리스트 변경

//AS-IS
<ul>
    <li key='a'>a</li>
    <li key='b'>b</li>
    <li key='c'>c</li>
</ul>

//TO-BE
<ul>
    <li key='d'>d</li> // a 삭제 후 새로운 d 추가
    <li key='b'>b</li> 
    <li key='c'>c</li>
    
</ul>
```

Memoization된 부분이 있다면 이전 가상 돔 객체과 비교하면서 새롭게 만들지 아니면 이전 가상 돔 객체 그대로 랜더하지 않을지 결정한다. deps를 기준으로 Memoization 여부를 결정할 수 있다. 얉은 복사로 비교하기 때문에 레퍼런스 기준으로 변경 여부를 확인한다.

\*useMemo vs useCallback vs React.memo

useMemo와 useCallback 모두 동일하게 memoization 하여 값을 리턴한다. 다만 useCallback의 경우 함수에 초점을 맞추어 제공하는 것이다.



#### 반영 Commit

렌더 Phase에서 flag를 달아둔 변경 사항들을 Real DOM에 반영한다. 이때 ref도 같이 심는다.



\*useEffect

useEffect는 커밋 Phase까지 완료하여 화면에 랜더링이 되고 난 후에 실행한다. 변형, 구독, 타이머, 로깅 또는 다른 부작용(side effects)에 사용하기 적합하다. 사용자에게 노출되는 DOM 변경은 사용자가 노출된 내용의 불일치를 경험하지 않도록 다음 화면을 다 그리기 전에 동기화 되어야 한다.

```jsx
useEffect(() => {}); // 랜더링되고 난 후 항상 실행
useEffect(() => {}, []); // componenetDidMount 최초 랜더링
useEffect(() => {}, [deps1, deps2]); // 최초 랜더링과 deps가 변경이 있을 때
useEffect(() => {return () => {}}, []); // componentWillUnmount
```

* [ ] MVC 패턴

### 상태 관리

* [ ] 제어 vs 비제어 컴포넌트
  * [ ] Ref
* [ ] state 비동기 vs 동기
* [ ] context API, zustand
* [ ] props vs state
* [ ] class vs function component (feat. hooks)

###

### 리액트란 무엇인가?

리액트는 컴포넌트 기반 UI 라이브러리이다. 컴포넌트 단위로 나누어 독립적으로 역할과 기능에 따라 관리하기 용이하며, 재사용성을 높일 수 있다. 리액트 내의 데이터는 트리 기준으로 위에서 아래로 단방향으로 흐른다. 그리고 상태에 따라서 랜더링하는 원칙을 갖고 있다. 가상 DOM을 이용해 변경사항만 빠르게 UI를 업데이트하고 최적화 시킬 수 있다.

#### 리액트를 사용하는 이유는 무엇일까?

넓은 생태계 및 다양한 라이브러리를 활용해 프레임워크화 할 수 있음 (Next.js 등)

많은 대기업에서 사용하고 있기 때문에 검증된 안정성

웹, 앱 등 다양한 플랫폼 지원

유저 친화적인 랜더링 (가상 DOM, SPA 등)

#### 컴포넌트란 무엇인가?

하나의 단위로 역할에 따라서 비즈니스 로직을 담거나 UI를 담아서 설계할 수 있다. 컴포넌트 기반의 코드는 재사용성을 높이고 코드 유지 보수 차원에서 수월할 수 있다.

#### 컴포넌트 설계는 어떻게 하는게 좋은가?

컴포넌트는 한가지 일만 하도록 설계하고자 한다. (SOLID SRP)&#x20;

비즈니스와 UI의 분리

#### 단방향 데이터란 무엇인가?

위에서 아래로 흐르며 자식 컴포넌트에서 데이터를 수정할 수 없다. 자식에서 부모의 상태를 변경하려면 props로 함수를  전달해 변경할 수 있다.



####







