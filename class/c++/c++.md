# C++ 기초

## 키워드와 식별자

### 키워드 Keyword

미리 정해 놓은 단어

다른 용도로는 사용할 수 없음

### 식별자 Identifier

키워드 외 변수, 함수, 클래스 이름 등을 구분하기 위해 만든 이름

첫 글자는 숫자가 아니여야함, `_$` 는 사용 가능함 그 외 특수문자 X

<table><thead><tr><th width="224">Naming Convention</th><th>i.e.</th></tr></thead><tbody><tr><td>Snake case</td><td>my_name</td></tr><tr><td>Camel case</td><td>myName</td></tr><tr><td>Pascal case</td><td>MyName</td></tr></tbody></table>



## 기본 자료형 및  변수

**기본 자료형**

고정소수점 Fixed-point 방식 (overflow 되면 안됨, 2진수의 경우 가장 오른쪽에 점 고정)

<table><thead><tr><th width="177">Data Type</th><th>Description</th></tr></thead><tbody><tr><td>정수 자료형</td><td><p><strong>문자</strong> char</p><p><strong>정수</strong> short &#x3C; int &#x3C; long &#x3C; long long</p><p>bool</p></td></tr><tr><td>실수 자료형</td><td>float, double, long double</td></tr></tbody></table>



**복합 자료형**

* 배열, 구조체 Struct, 클래스 Class, 열거형 Enum, 공용체 Union
* 포인터, 참조

