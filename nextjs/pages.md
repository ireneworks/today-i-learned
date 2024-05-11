# Pages

**CSR**

1. 서버에서 HTML/CSS 리소스 다운 후 빈 HTML 노출
2. JS 다운로드
3. 동적으로 DOM 생성
4. 유저 인터렉션 가능

\*반대로 TTI가 중요한 경우 사용 적합



**SSR**

1. 서버에서 만들어진 HTML 파일을 다운로드 후 완성된 화면 노출
2. JS 다운로드
3. 유저 인터렉션 가능

\*커머스, 신문 등 TTV가 중요한 프로덕트의 경우 사용 적합

***

Next.js는 두개를 활용하여 애플리케이션을 구성할 수 있다.

SSR을 이용한다는 것은 data fetching까지 마친 화면의 코드를 서버에서 받아 랜더링한다는 것을 의미한다.

즉, 네트워크 탭에서 확인해보면 request 보내는 것다는 것을 확인할 수 있다.

\*현재 styled-components가 입혀지지 않은 상태의 화면을 볼 수 있어 어떤 문제인지 확인 필요



어떻게 SSR을 적용하는지 확인해보자





`getStaticProps`

Fetch data at build time, pre-render for Static Generation

빌드 시 고정되는 값, 빌드 이후에는 변경 불가



`getServerSideProps`

Fetch data on each request. Pre-render for Server-side Rendering

빌드랑 상관 없이, 매 요청마다 데이터를 서버로 부터 가져옴

