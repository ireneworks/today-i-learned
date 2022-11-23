---
description: Cascading Style Sheets
---

# 스타일 CSS

CSS로 하는게 비용이 적게 들기 때문에 가능하다면 CSS로 처리하는게 좋다.

```css
/* absolute는 최대한 지양하고 다른 방법을 활용해보자 */

main {
    display: table;
    height: 540px;
    
    div {
        display: table-row;
        height: 60px;
    }
}
```

```css
/* ellipsis(truncation) */

dt {
    overflow: hidden;
    word-break: break-all;
    text-overflow: ellipsis;
    white-space: nowrap;
}

/* 줄 단위 */
dt {
    overflow: hidden;
    word-break: break-all;
    text-overflow: ellipsis;
    -webkit-line-clamp: 2;
    -webkit-box-orient: vertical;
}
```

```css
/* 반응형은 media query, min/max 하나로 정해서 이용하기 */

@media screen and (min-width: ${NARROW_PC}) {
    display: none;
}

/* 해당 미디어에만 적용 */

@media print only (min-width: ${TABLET}) {
    background: #111111;
}
```

```css
/* 의미없는 이미지/아이콘은 백그라운드 처리 */

div {
    background: transparent url(${heartIcon}) left 12px bottom 12px / 20px no-repeat;
}
```

```css
/* 클릭 영역을 고려해서 Margin, Padding 설정하기 */

a {
    padding: 12px 0 24px;
}
```

```css
/* 선택자를 잘 활용하기 */

div > span {
    font-weight: 500;
}

div + span {
    color: #888888;
}
```

```css
/* 요소 뒤에 추가 (&는 this와 유사) */

&::after {
    content: "|";
}

/* 마지막 요소 선택 */

&:last-child::after {
    display: none;
}
```

```css
/* flex 단 나누기 */

.parent {
    display: flex;
    
    .child {
        flex: 1 1 50%;
        gap: 24px;
    }
}
```

```css
/* 윈도우에서는 다르게 보이기 때문에 원하는 곳에만 스크롤 바가 생길 수 있게 */

div {
    overflow-x :hidden;
}
```

```css
/* MOBILE FIRST라면 default는 MOBILE에 맞추어 작성하기 */

main {
    background: #ffffff;
    
    @media screen and (min-width: ${NARROW_PC}) {
        background: #eeeeee;
    }
}
```

```css
/* li는 inline 속성이기에 button의 영역을 잡을 땐 block 등으로 변경 필요 */

li {
    display: block;
    
    button {
        /* 버튼 스타일 */
    }
}
```

```css
/* flex 내 자식 요소 grow, shrink에 대해서 이해하기 */

parent {
    display: flex;
    
    children {
        flex: 1 1 100%; 
    }
}
```
