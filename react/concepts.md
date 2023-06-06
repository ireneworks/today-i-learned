# Concepts

**Nesting components**

리액트는 **컴포넌트들의 집합체**이다. 컴포넌트라 하면 UI(User Interface)로 자신의 로직과 스타일을 갖고 있다. 예를 들면 아주 작은 단위의 버튼부터 하나의 페이지까지 다양하다.

\-> Atomic design system과 잘 부합하는 것 같다. [1)](https://blog.prototypr.io/what-is-this-thing-atomic-design-i-keep-hearing-about-3b7bd0edddcd)

리액트 컴포넌트는 자바스크립트의 함수를 사용하며 마크업을 반환한다. 또한, HTML 태그와 구분할 수 있도록 리액트 컴포넌트는 대문자를 사용한다.&#x20;

```jsx
// JSX 내 { } escape 문자를 통해 자바스크립트 값들을 넣을 수 있다.
const Button = ({onClick}) => {
    return (
        <button onClick={onClick}></button>
    )
}

// export default 키워드는 파일 내 메인으로 반환할 것을 의미한다.
export default const Page = () => {
    const onClick = () => {
        ...
    }

    return (
        <>
            <h1>Payment</h1>
            <Button onClick={onClick}/>
        </>
    )
}
```

리액트 컴포넌트는 여러개의 JSX 태그를 반환할 수 없고 하나의 감싸진 JSX 태그만을 반환할 수 있다.&#x20;

구체적으로 정해진 바는 없지만 가장 쉽게 `className`을 통해 스타일링 할 수 있다.&#x20;



리액트에서는 `if`를 사용해 렌더링 분기처리 할 수 있다.

```jsx
const Input = ({isLoggedIn, username}) => {
    const content = isLoggedIn ? <Admin /> : <Login />
    
    return(
        <div>
            {content}
            {username && (
                <span>{username}</span>
            )}
        </div>
    )
}
```
