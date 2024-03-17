# z-index

<div align="left">

<figure><img src="../.gitbook/assets/1_uGPV3qEF7yBq4PD0zua19A (3).png" alt="" width="375"><figcaption><p>z axis <a href="https://velog.io/@kskim625/%ED%9A%A8%EC%9C%A8%EC%A0%81%EC%9D%B8-%EC%95%A0%EB%8B%88%EB%A9%94%EC%9D%B4%EC%85%98-2">1)</a></p></figcaption></figure>

</div>

css 프로퍼티 중 z-index는  z축 순서를 지정할 수 있다. 웹에서 z축은 앞으로 튀어나와보이게 조정할 수 있다. 따라서 모달, 툴팁 등에서 자주 이용된다. 쉽게 생각해보면 레이어의 순서를 조정하여 앞으로 튀어나와보이게 하는 것이다.

```html
<div class='red'> // z-index 1
    <div class='blue' /> // z-index 50
</div>
<div class='orange' /> // z-index 20
<div class='green' /> // z-index 10
```

어떤 순서대로 쌓이는지 확인해보면 당연히 여러가지 css 속성에 따라 달라질 수 있으나 순수히 `z-index` 만 놓고 본다면 다음과 같을 것이다. 부모가 가진 stacking context 내에서만 blue는 유효하기 때문에 부모끼리의 `z-index`와는 관련없다.

<div align="left">

<figure><img src="../.gitbook/assets/스크린샷 2024-03-17 오후 10.21.45.png" alt="" width="188"><figcaption><p>element z index order</p></figcaption></figure>

</div>



{% embed url="https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_positioned_layout/Understanding_z-index/Stacking_context" %}
