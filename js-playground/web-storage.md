# 브라우저 저장소 Web Storage

두 저장소 `key: value` 형태의 문자열 string 값으로 저장한다.



**Cookie**

Cookie는 4KB로 작은 데이터를 저장할 수 있고, 서버와 통신한다. 쿠키는 주로 서버가 유저를 기억하기 위한 용도로 사용된다. HTTP 프로토콜은 stateless이기 때문에 `request > response`가 끝나고 나면 통신을 끊고 그 다음 통신을 해도 이전 내용을 기억할 수 없기 때문이다. (주로 사용자의 언어, 다크모드 등의 내용을 저장)



**Web Storage**

Web Storage는 Local, Session으로 나뉘어져 있다. 5MB 정도로 쿠키에 비해서 큰 데이터를 저장 할 수 있고, 서버로 전송되지 않는다. 굳이 서버로 전송할 필요가 없는 데이터라면 보안과 속도를 위해 이용하며, 웹 성능에 영향을 주지 않고 큰 데이터를 저장할 수 있다. **Local Storage**는 유효기간이 없지만, **Session Storage**는 창을 닫으면 초기화된다.[4)](https://geonlee.tistory.com/127)

실제로 프로젝트에서도 Local Storage를 사용했었고, 일회성 모달과 로그인 여부를 확인하기 위해 저장했다.



**Browser Cache**

Browser Cache는 브라우저에서 웹 리소스의 사본을 저장하는 방식으로 이미지, HTML, CSS, JS 등의 에셋이 있다. 서버와 클라이언트가 통신을 하다보면 지연될 수 있고 이 간극을 줄이기 위해 브라우저 캐시가 있다.&#x20;
