# 변수 Variable

## 식별자 Identifier

![](<../.gitbook/assets/IMG\_0363 (1).PNG>)

* `value` 는 메모리 주소에 값이 담겨있는 위치를 식별하기 위해 붙힌 이름
* `value` 식별자는 메모리 주소를 기억

###

## 원시타입 Primitive Type

```javascript
var x = 5 
// Number, String, Boolean, null, undefined, Symbol
```

<figure><img src="../.gitbook/assets/IMG_0336.PNG" alt=""><figcaption><p>Immutable value</p></figcaption></figure>

* 원시 값은 변경 불가능(Immutable value)
* 메모리 주소를 변경해서 값을 변경, 원천 데이터는 변경할 수 없음

###

## 객체/참조타입 Object/Reference Type

```javascript
const arr = [1, 2, 3]; 
// Object
```

`arr`은 재할당 불가능한 변수 값의 주소를 재할당할 수 없으나, 주소 안의 값은 변경할 수 있다.

###

## 스코프 Scope

```javascript
var a = 100;
if (a>0) {
    var a = 200;
    console.log(a); //200
}
console.log(a); //200

let b = 100;
if(b>0) {
    let b = 200;
    console.log(b); //200
}
console.log(b); //100

```

`let`은 함수와 같은 블록 내 스코프를 가진다.
