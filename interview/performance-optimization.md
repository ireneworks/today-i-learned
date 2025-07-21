# Performance optimization

### **Question**

Can you walk me through a project you've worked on as a front-end developer? \
What technologies did you use, and what challenges did you face during development?



### 발견 Observation

신규 유저 유입 프로젝트를 진행중이었고, 첫 메인 페이지의 로딩(랜더링)속도가 굉장히 느림

As part of our new user acquisition goal, I conducted a development investigation into the performance of the gateway page. I found that the initial rendering performance of the gateway page was very poor.

### 문제 Problem Statement

1. All of the assets were in the `public folder`&#x20;
   1. It's unnecessary to deploy all assets for every change, especially with frequent updates to items like banners or product iterations, making dynamic file management inefficient.
   2. Static assets such as logo and favicon that does not need frequent updates





1. `public` 폴더에 모든 에셋을 포함하고 있음
   1. 파일 변경이 필요한 경우 지속적인 배포 필요 (예를 들면 배너, 프로덕트의 잦은 iteration 등) 동적 파일 관리 측면에서 비효율적
   2. 정적이라 하면 로고, 파비콘 등 비교적 긴 시간 동안 변경이 없는 경우 (헤더, 푸터, terms 등)
2. 모든 에셋이 비 최적화
   1. next/image 태그를 사용하지 않음 (next 이미지 설정이 akamai를 사용하는데 akamai 설정이 안되어 있어 CORS 에러 발생)
   2. 처음 랜딩 시 페이지 로딩 시간이 길어지고 페이지 성능이 저하되어 고객에게 나쁜 경험 제공



### 해결 Solution

1. 에셋 분리
   1. 정적 자원과 동적 자원을 분리하고 동적 자원을 S3에서 가져오도록 수정
      1. S3 API 연동 (디자인 팀과 에셋 올리는 방법 설정, 이름으로 불러올 수 있게 룰 설정, 에셋 유효기간 설정)
2. 에셋 최적화
   1. 이미지, 영상을 WebP, WebM으로 변경
      1. 아이콘은 디자인 시스템으로 제공
   2. next/image 태그 사용
      1. TTV 최적화를 위해 placeholder, priority, layout 등을 이용한 룰 설정 (LCP, CLS 고려)



### 성과 Metrics

LightHouse

* performance 약 68% 증가
* CLS 약 99% 감소
* LCP 약 91% 감소
* TTV 약 83% 감소



Acquisition

* 약 1.96배 증가 (하지만 다양한 변수가 존재함)

