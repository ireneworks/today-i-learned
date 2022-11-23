---
description: NPM vs Yarn Berry
---

# 노드 패키지 매니저 Node Package Manager

Node.js는 자바스크립트를 이용한 서버 사이드 언어



npm !== Node.js(편의상 노드)



노드는 single thread 단순 연산

자바는 multi thread 큰 연산



대부분은 노드, php (스크립트 언어) -> 자바



노드 위에서 도는 노드 패키지 매니저 npm



npm public registry 에서 일반적으론 다운 받고,

private  repo인 verdaccio 등도 있음



npm script 알아야함 (명령어)

npx 중요



```
npm init //package.json > cra는 자동 생성
npm outdated //패키지 중에 업데이트가 필요한게 있는지
npm start (scripts)
npx  // 

.bin 명령어 등록 > 해야 cra에서 쓸 수 있음 패키지 등록
npx > 
--package 어떤 명령어로 할지 선택??

npx 레파지토리(registry)에서 임시로 불러오고 그 파일은 사라진다
예를 들면 cra인데, 항상 최신의 버전의 cra 만들기 위해 cra는 npx로 설치됨
글로벌에 최신 버젼을 설치 후 cra 완료되면 삭제됨

script //npm start 제외하고 npm run 쓰고 커스텀 명령어는 무조건 붙히고 사용해야함

```



```
Dependency
devDependency
peerDependency
```

각 디펜던시는 모듈(패키지)를 만들어서 배포할 때 중요하게 쓰이는 부분

제공하는 사람은 필요하고

받는 사람은 필요없음 (npm 패키지를 받아서 쓰는 사람)



테스트/개발/웹팩/프리티어/린트 개발 과정에서 필요한 거는 devDep

dep 받는 사람도 필요한 것

peerDep 이 패키지를 사용하려고 할때 어떤 패키지 최소 버젼이 필요한 것을 알려줌



버전은 주로

짝수 stable LTS(Long Term Support)

홀수 exp 실험적인 버전



nvm node version management

여러 버전 사용하려고할때 이용

노드는 내 데스크톱에 깔려있음

```
nvm use v14 //어떤 버젼을 이용할 건지
nvm 설치하고 node를 설치해야함 //nvm에서 이미 설정된 노드를 수정하는게 복잡하기 때문에 무조건 nvm 먼저 설치

cli에서 #은 주석
```





### Yarn이란

노드를 위한 새로운 패키지 매니저

yarn > yarn berry  LTS 최신 버젼&#x20;



왜 나왔나

* 디펜던시 관계가 비효율적이다

node\_modules

* 패키지를 계속 찾기 위한 비효율적인 동작
* 의존성 문제가 발생 > 다른거 불ㄹ러올수도잇고 버젼을
* 비효율적인 설치,&#x20;

i/o 인풋 아웃풋 >&#x20;



phantom dep

debuped 중복된

yarn은 호이스팅 debuped 라고하고 하나만 깔고 바라보고 잇음

첫번째 디펜던시가 6버젼이면 그걸로 깔음

dependcy tree



패키지를 사용하고 있따가 삭제

그럼 호이스팅 디펜던시 로 된것도 삭제

* 그러면 그냥 앱에서 사용하던 호이스팅 디펜던시가 사라져서



yarn이 나왔는데

plug n play pnp



캐싱을 시키자

집파일로 만들어서 캐싱

노드모듈스 안쓴다

npm i yarn -g

yarn set version berry&#x20;

yarn path 글로벌이더라도 프로젝트별로 바라보는 버젼이 다름

package.json > packageManager 생김



yarn install (npm install과 같음)

또는 yarn



yarn start



노드모듈스가 얀을 봄

nodeLinker: node-modules



패키지 단위로 해당 프로젝트에서만

얀은 노드모듈스 만들지 않음



.pnp.cjs 에서 의존성 정보가 기록됨

노드모듈스는 각 파일로 찾아야하는데 얀은 저 파일에서만 보면됨



import 하면

노드모듈스는 하나하나 파일에서 찾아봄

파일 읽는건 리소스가 큼 비용이 크다



얀은 바로 import 해와서 사용할 수 있음



캐시를 바로 깃에 같이 올림



// 인텔리제이 안될때

.iml 파일 삭제



의존성 문제가 있으면 삭제하고 다시 설치



zero-install 가능









