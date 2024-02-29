# query parameter와 fetch 고찰

state 값만으로도 계속 데이터 fetch

query parameter

```
// state update
// data fetch
// query parameter update
```

유저가 이벤트를 발생시키면 상태가 변경되어 상태가 변경되고 데이터를 fetch 하고 쿼리를 변경시킨다.

만약 쿼리가 먼저 변경된다면 다음과 같은 문제점이 발생할 수 있기에 데이터를 먼저 fetch 하는 것이 좋은 UX라 생각된다.  데이터 fetch 시 에러가 발생해도 쿼리를 먼저 변경하지 않기 때문에 화면의 갭을 줄일 수 있다.

* 데이터 fetch 중 쿼리가 변경 될 수 있음
* 데이터 로딩으로 인한 변경되어야 할 화면과의 갭 발생

```
// AC

1. 상태가 변경될 때 마다 데이터 fetch
2. 이니셜 랜더 때 쿼리 전달하지 않고 fetch
3. 쿼리가 변경될 때 마다 데이터 fetch
```

생각해 볼 수 있는 요구사항은 총 3가지가 있을 것이다. 2번의 경우 커머스 필터 UX를 확인해보면 이니셜 랜더에서는 쿼리를 변경하지 않고 필터를 한번이라도 이용하면 그때 쿼리에 업데이트 한다.

```jsx
// AC 1. 상태가 변경될 때 마다 데이터 fetch

useEffect(() => {
    // data fetch
    // query update
}, [state])
```



유즈케이스 2번에서 해야할 일은 이니셜 랜더시 default 값으로 데이터를 fetch 해야한다. 하지만 1번에서 데이터를 fetch 할 때 state 값으로 쿼리를 날리고 있기에 state 값을 넣지 않고

```
// data fetch
// query parameter update
```

