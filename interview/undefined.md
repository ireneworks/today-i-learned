# 목록

## 브라우저 동작원리

1. 유저가 브라우저에 입력한 주소는 DNS 서버에서 실제 해당 서버가 위치한 곳으로 연결
2. 실제 서버에서 HTML/CSS/JS 리소스 다운로드
3. HTML/CSS를 파싱해서 HTML은 DOM 트리, CSS는 CSSOM 트리를 생성
4. 생성한 두개의 트리를 합쳐 랜더트리를 생성
5. 생성된 랜더트리의 각 노드들을 계산해서 위치, 크기 등과 같은 레이아웃을 만듦
6. paint 단계에서 각 노드들을 실제 화면에 그림

유저가 이벤트를 발생시켜 새로운 노드가 추가되거나 변경된다면 reflow, repaint가 일어난다. 많은 reflow와 repaint가 일어나게 되면 성능상 이슈가 발생한다. 많이 발생하지 않도록 최적화 시켜야한다.&#x20;



**최적화 방법** [**1)**](https://beomy.github.io/tech/browser/reflow-repaint/)****

* 불필요한 태그 사용은 지양하고 최소한의 태그 사용으로 작게 만들기
* 애니메이션의 경우 초당 프레임이 지속적인 reflow를 발생시키기 때문에 퀄리티와 퍼포먼스에서 타협점을 찾는다.
* 변경이 필요한 경우, 가장 하위 노드에 적용하면 reflow 영향을 최소화 할 수 있다.



| Reflow                                                | Repaint                                                                         |
| ----------------------------------------------------- | ------------------------------------------------------------------------------- |
| `position`, `width`, `height`, `margin`, `padding` 등  | `background`, `color`, `box-shadow`, `border-radius`, `outline`, `visibility` 등 |



## CORS(Cross-origin Resource Sharing)

<figure><img src="../.gitbook/assets/mdn-url-all.png" alt=""><figcaption><p>URL <a href="https://developer.mozilla.org/en-US/docs/Learn/Common_questions/What_is_a_URL">2)</a></p></figcaption></figure>

교차 출처 리소스 공유는 동일한 URL이 아닌 다른 출처에서 데이터를 주고 받는 것을 허용하는 정책이다.&#x20;

**프로토콜**, **호스트**, **포트**가 모두 같아야 동일한 출처이다.



실제로 리엑트 프로젝트를 하면서 CORS 이슈를 겪었는데, 이를 해결하기 위해 `package.json` 에서 `proxy` 설정으로 해결했다.

```javascript
//package.json

"proxy": "http://localhost:8888"
```

<figure><img src="../.gitbook/assets/제목 없는 다이어그램.jpg" alt=""><figcaption><p>Proxy 동작 원리</p></figcaption></figure>

##

## CSR(Client Side Rendring) SSR(Server Side Rendering)

**CSR 동작**

1. 서버에서 HTML/CSS 리소스 다운 후 빈 HTML 노출
2. JS 다운로드
3. 동적으로 DOM 생성
4. 유저 인터렉션 가능

**SSR**

1. 서버에서 만들어진 HTML 파일을 다운로드 후 완성된 화면 노출
2. JS 다운로드
3. 유저 인터렉션 가능



| 항목            | CSR                          | SSR                            |
| ------------- | ---------------------------- | ------------------------------ |
| **페이지 구성 방식** | SPA(Single Page Application) | MPA(Multiple Page Application) |
| **페이지 로딩 시간** | 초기 로딩 느림 이후 TTV, TTI 갭 없음    | 초기 로딩 속도 빠름, 페이지 로딩 시 깜빡임      |
| **SEO 대응**    | 빈 HTML로 SEO 불리               | 완성된 HTML로 SEO 유리               |
| **서버 자원 사용**  | 서버 부하 적음                     | 서버 부하                          |
| **애플리케이션**    | 인터렉션이 많은 애플리케이션              | 커머스, 신문 등                      |

진행했던 프로젝트는 커머스 비즈니스이기 때문에 SEO가 중요한 플랫폼이고 이를 위해 Next.js를 도입했다.



## attribute, property

```html
<input value="name" />
```

태그 내 속성을 의미하는 `attribute`

DOM 생성 후 속성을 의미하는 `property` , DOM을 조작해 `property`를 변경할 수 있다.





## Cookie, Web Storage