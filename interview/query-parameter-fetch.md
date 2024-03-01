---
description: 쿼리 파라미터와 데이터 가져오기에 대한 고찰
---

# Best practice for query parameter  and fetch

### 필터 이용 시 쿼리 파라미터를 같이 변경해줘야해?

상태를 기준으로 할지 쿼리 파라미터를 기준으로 데이터를 fetch할지 고민하다가 문득 쿼리도 업데이트 해야하나? 라는 생각이 들어 고민해보았다. 프로덕트 요구사항에 따라 달라질 수 있으나, 일반적인 커머스 필터 UX를 고려하여 접근해본다면 크게 다음과 같은 사용자 경험을 제공할 수 있을 것이다.

* 보고 있는 데이터 공유 및 북마크
* 앞/뒤로가기로 쉽게 원하는 것을 찾을 수 있음

커머스 도메인에서는 고객이 쉽게 상품을 찾는게 중요하기 때문에 빠르게 상품에 접근하고 계속 탐색을 이어나갈 수 있는 경험을 유지하는 것이 중요하다.

### 어떻게 데이터 fetch를 하는게 좋을까?

```
// AC

1. 상태가 변경될 때 마다 데이터 fetch
2. 쿼리가 변경될 때 마다 데이터 fetch
3. 이니셜 랜더 때 쿼리 전달하지 않고 fetch
*  필터 적용시 해당 필터가 다른 필터 만큼 페이지 수가 다르다면?
```

#### 1번 커먼 유즈케이스&#x20;

```jsx
// state update
// data fetch
// query parameter update

const [params, setParams] = useState('all');

useEffect(() => {
    // data fetch with params
    // query update
}, [params])
```

유저가 이벤트를 발생시키면 상태가 변경되고 데이터를 fetch 한 후에 쿼리를 변경시킨다.

만약 쿼리가 먼저 변경된다면 다음과 같은 문제점이 발생할 수 있기에 데이터를 먼저 fetch 하는 것이 좋은 UX라 생각된다.  데이터 fetch 시 에러가 발생해도 쿼리를 먼저 변경하지 않기 때문에 화면의 갭을 줄일 수 있다.

* 데이터 fetch 중 쿼리가 변경 될 수 있음
* 데이터 로딩으로 인한 변경되어야 할 화면과의 갭 발생

#### 2번 쿼리가 변경될 때 마다 데이터 fetch

```jsx
// query parameter update
// state update
// data fetch

const [params, setParams] = useState('all');
const {search} = useLocation();

useEffect(() => {
    // get query parameter
    // state update
}, [search])

useEffect(() => {
    // data fetch with params
    // query update
}, [params])
```

ㅋ
