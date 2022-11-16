# 패키지 매니저 NPM

자스 이용한 서버 사이드 랭기지

npm !== node os 써봣나

노드는 single thread 큰 연산은 자바가 , 단순 연산은 노드로

java = multi thread language&#x20;



노드  php 스크립트 언어 > 자바



패키지 관리 npm

노드에서 도는 패키지 매니저&#x20;



npm  resistry

npm public registry&#x20;

verdaccio private repo



npm s cript 알아야함

npx&#x20;



```
npm init //package.json > cra는 자동 생성
npm outdated
npm start (scripts)
npx  // 

.bin 명령어 등록 > 해야 cra  쓸 수 있음 패키지 등록
npx > 
--package 어떤 명령어로 할지 선택

npx 레파지토리에서 임시로 불러오고 그 파일은 사라진다
항상 최신의 버전의 cra 만들고 싶다
글로벌에 최신꺼를 설치후 cra 완료 되면 삭제됨

script {start 제외하고 npm run 쓰고 커스텀 명령어는 무조건 붙혀서}

```



```
Dependency
devDependency
peerDependency
```

모듈을 만드러서 배포할 때 문제

제공하는 사람은 필요하고

받는 사람은 필요없음 npm 패키지를 받아서 쓰는 사람

테스트/개발/웹팩/프리티어/린트 개발 과정에서 필요한 거는 devDep

dep 받는 사람도 필요한 것

peerDep 이패키지를 사용하려는거가 어떤 패키지 최소 버젼



버전은&#x20;

짝수 stable LTS

홀수 exp 실험적인 버전



nvm

node version management

여러 버전 사용하려고할때

노드는 내 데스크톱에 깔려있음

nvm use  v14

nvm  > node 설치해야함 (수정하는 과정이 복잡하기 때문에 무조건 nvm 먼저 설치)

node 명령어는&#x20;



cli #은 주석





yarn이란

노드 js를 위한 새로운 패키지 매니징

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









