# Performance optimization

### **Question**

Can you walk me through a project you've worked on as a front-end developer? \
What technologies did you use, and what challenges did you face during development?



### 발견 Observation

As part of our new user acquisition goal, I conducted a development investigation into the performance of the gateway page. I found that the initial rendering performance of the gateway page was very poor.



### 문제 Problem Statement

1. All of the assets were in the `public folder`&#x20;
   1. It's unnecessary to deploy all assets for every change, especially with frequent updates to items like banners or product iterations, making dynamic file management inefficient.
   2. Static assets include items like logos and favicons that don't require frequent updates.
2. All of the assets are not optimized
   1. Not used next/image tag. (CORS errors occurred because Akamai was not configured for Next.js images.)
   2. The initial page loading time increased, and poor page performance led to a bad user experience.



### 해결 Solution

1. Asset seperation
   1. 정적 자원과 동적 자원을 분리하고 동적 자원을 S3에서 가져오도록 수정
      1. S3 API 연동 (디자인 팀과 에셋 올리는 방법 설정, 이름으로 불러올 수 있게 룰 설정, 에셋 유효기간 설정)
2. Asset optimization
   1. 이미지, 영상을 WebP, WebM으로 변경
      1. 아이콘은 디자인 시스템으로 제공
   2. Use next/image tag
      1. TTV 최적화를 위해 placeholder, priority, layout 등을 이용한 룰 설정 (LCP, CLS 고려)



### 성과 Metrics

LightHouse

* performance 약 68% 증가
* CLS 약 99% 감소
* LCP 약 91% 감소
* TTV 약 83% 감소



Acquisition

* 약 1.96배 증가 (하지만 다양한 변수가 존재함)

