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

웹은 동일 출처 정책(Same-Origin Policy)에 기반한다. 해당 정책은 웹 페이지가 다른 출처의 리소스에 진입하는 것을 제한하여 악의적인 스크립트에 의한 사용자 정보 노출 및 변조를 방지하고자 보안의 측면에서 기반하고 있다. 즉, 웹 브라우저를 사용하는 유저를 보호하기 위함이다. 보안 문제가 발생하게 된 이유는 과거 웹 페이지는 보기만 할 수 있었던 시대에서 유저의 요구사항에 맞춰 점점 발전하면서 자바스크립트와 DOM API가 개발되고 고도화되면서 많은 기능들이 생겨났다.&#x20;



서버는 Response에 클라이언트는 Request에 CORS 옵션을 작성해주면 된다.





XSS, CSRF(XSRF) 보안 취약 방어

&#x20;
