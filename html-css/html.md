---
description: Hyper Text Markup Language
---

# 구조 HTML

{% hint style="info" %}
"Web accessibility means that websites, tools, and technologies are designed and developed so that people with disabilities can use them." **W3C**
{% endhint %}

**모든 사용자가 제외되지 않고** 웹을 이용할 수 있도록 접근성을 준수해야한다. 스크린 리더를 통해 웹을 읽어나가는 과정에서 각각의 요소를 **시맨틱한 태그를 이용해 마크업한다면 접근성을 높일 수 있을 것이다.** 또한 **브라우저의 호환성**을 고려하 **UX Writting**도 신경쓰도록 한다.

```html
<!-- 의미 있는 텍스트인 경우 -->

<p>검색 결과가 없습니다.</p>
```

```html
<!-- dl에는 dt, dd가 아닌 요소는 포함될 수 없음 (div, script, template 제외) -->

<dl>
    <div>
        <dt>단어</dt>
        <dd>설명이 들어갑니다.</dd>
    </div>
</dl>
```

```html
<!-- list -->

<ul>
    <li>
        <a href="#">순서가 없는 링크 1</a>
    </li>
    <li>
        <a href="#">순서가 없는 링크 2 </a>
    </li>
</ul>
```

```html
<!-- 이미지를 볼 수 없는 경우 -->

<img src={image} alt="이미지를 볼 수 없을 때 나올 설명" title="툴팁에 나올 설명" />
```

```html
<!-- 최대한 간결하게 -->

<button>확인</button>
```

```html
<!-- section vs div -->

<section>주로 헤딩 태그를 포함하고 챕터, 검색 결과, represent a standalone, atomic unit</section>
<div>특별한 의미 없는 태그로 레이아웃과 스타일을 주기 위함 또는 정말 사용할 태그가 없을 때 사용해보자</div>
```
