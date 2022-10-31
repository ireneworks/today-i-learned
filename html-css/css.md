---
description: Cascading Style Sheets
---

# CSS

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
/* 말 줄임표 */

dt {
    overflow: hidden;
    word-break: break-all;
    text-overflow: ellipsis;
    white-space: nowrap;
}
```

```css
/* 반응형은 media query, min/max 하나로 정해서 이용하기 */

@media screen and (min-width: ${NARROW_PC}) {
    display: none;
}
```

```css
/* 의미없는 이미지/아이콘은 백그라운드로 노출하기 */
div {
    background: transparent url(${heartIcon}) top 12px / 20px no-repeat;
}

/* 클릭 영역을 고려해서 Margin, Padding 설정하기 */
a {
    padding: 12px 0 24px;
}

/* 선택자를 잘 활용하기 */
div > span {
    font-weight: 500;
}

div + span {
    color: #888888;
}

/* 요소 뒤에 추가 */
&::after {
    content: "|";
}

/* 마지막 요소 선택 */
&:last-child::after {
    display: none;
}

/* flex */
.parent {
    display: flex;
    
    .child {
        flex: 1 1 50%;
        gap: 24px;
    }
}

/* 윈도우에서는 다르게 보이기 때문에 원하는 곳에만 스크롤 바가 생길 수 있게 */
div {
    overflow-x :hidden;
}

/* MOBILE FIRST라면 default는 MOBILE에 맞추어 작성하기 */
main {
    background: #ffffff;
    
    @media screen and (min-width: ${NARROW_PC}) {
        background: #eeeeee;
    }
}
```
