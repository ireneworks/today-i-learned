# 교차 출처 리소스 공유 CORS

CORS(Cross Origin Resource Sharing)는 브라우저에서 실행 중인 어플리케이션이 자신의 출처(도메인, 프로토콜, 포트 등)와 다른 출처의 자원에 접근할 수 있도록 교차 출처 HTTP 요청을 실행한다.

## URL 구조

![1)](../.gitbook/assets/0.png)

### 프로토콜

* HTTP(Hyper Text Transfer Protocol) 프로토콜(규약)
* 웹에서 클라이언트와 서버가 어떤 방법으로 자원에 접근할 지 알려줌
* http/https 말고도 mailto, ftp 등 다양한 프로토콜 있음 [1)](https://hanseul-lee.github.io/2020/12/24/20-12-24-URL/)

### 도메인 Host

* IP 주소를 대신해서 사용하는 주소
* DNS(Domain Name System) 서버를 이용해서 IP와 도메인을 매칭 > DNS가 `coupang.com` 주소를 IP 주소로 변환
* &#x20;`example.com`  메인 도메인, `www` 는 서브 도메인

### Port

* http는 80번, https는 443번
* 포트는 옵셔널로 숨겨진다.



### 자신의 출처 Origin Resource

**프로토콜+도메인 이름+포트** `https://www.coupang.com:443`

이 중에서 하나라도 다르면 정책을 위반한다.



## CORS 정책의 배경

웹 브라우저는 동일 출처 정책 SOP(Same-Origin Policy)에 기반한다. 해당 정책은 웹 페이지가 다른 출처의 리소스에 진입하는 것을 제한하여 악의적인 스크립트에 의한 사용자 정보 노출 및 변조를 방지하고자 보안의 측면에서 기반하고 있다. 즉, 웹 브라우저를 사용하는 유저를 보호하기 위함이다.&#x20;

과거 웹 페이지는 보기만 할 수 있었던 시대에는 `웹 브라우저 <> 서버` 와의 통신만으로 충분했기 때문에 다른 사이트에 요청을 날리는 것은 악의적인 행동이라 보았기 때문에 SOP 정책을 만들게 된 것이다. 하지만 유저의 요구사항에 맞춰 어플리케이션으로 발전하면서 다양한 요청이 필요하나 SOP 정책으로 인해  이를 해결하기 위해 다음과 같은 방법을 이용했다.

<figure><img src="../.gitbook/assets/스크린샷 2024-02-27 오전 11.43.11.png" alt=""><figcaption><p>CORS 정책이 없던 시ㄹ</p></figcaption></figure>

ㄱ, CORS 정책을 만들게 되었다.

#### 보안 문제라면 어떤게 발생 할 수 있는데?

XSS, CSRF(XSRF) 등으로 우리가 만든 웹에서 해커가 심어놓은 코드가 실행하여 개인정보를 가로챌 수 있다.&#x20;



서버는 Response에 클라이언트는 Request에 CORS 옵션을 작성해주면 된다.





{% embed url="https://blog.areumsheep.vercel.app/contents/why-cors/" %}

{% embed url="https://inpa.tistory.com/entry/WEB-%F0%9F%93%9A-CORS-%F0%9F%92%AF-%EC%A0%95%EB%A6%AC-%ED%95%B4%EA%B2%B0-%EB%B0%A9%EB%B2%95-%F0%9F%91%8F" %}
