---
description: 연속된 동형 자료형
---

# 배열 Array

배열은 \<index, value>쌍의 집합이다.

배열의 크기는 타입에 따라 정해져 있으며, 동적 할당의 경우 overflow가 발생할 수 있다.

```cpp
// 배열의 타입과 길이와 값 입력
int arr[4] = {1, 2, 3};

// arr.length 총 크기 / 자료형
int length = sizeof(arr) / sizeof(arr[0] || int)
```

`int` 는 4바이트(8비트 \* 4 = 32비트)로 `arr`의 크기는 12바이트이다.

크기를 계산하는 방법은 16바이트 / 4바이트 = 4 이다.

arr\[0] 으로부터 값을 구하려면 int의 크기 4바이트 \* n (인덱스) 이다.



![](<../../.gitbook/assets/img (1).png>)



#### 추상 자료형 Abstract Data Type (ADT)

어떤 추상화된 자료형에 대해 어떤 연산이 필요한지 명세를 정의하는 것이 ADT이다.

기본적으로 제공되는 메소드를 통해 조합해서 필요한 연산을 정의한다.

리스트 내 값 삭제시 인덱스를 기준으로 값을 모두 이동하지 않고 포인터를 통해 앞 뒤 참조를 변경한다.

{% embed url="https://whyhard.tistory.com/5" %}

{% embed url="https://blog.naver.com/PostView.naver?blogId=nanf3302&logNo=221939911465&parentCategoryNo=188&categoryNo=&viewDate=&isShowPopularPosts=true&from=search" %}

