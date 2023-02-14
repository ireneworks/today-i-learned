# 변수 Variable

변수란 데이터를 관리할 수 있는 방법이다. 데이터는 메모리 힙 Memory Heap 임의의 위치에 저장되고 저장된 데이터의 주소 값을 변수가 기억하고 있다. 변수를 사용할 때는 변수가 기억하고 있는 메모리 주소에서 데이터를 불러와 변수에 할당한다. 할당 할 때는 데이터 타입에 따라 `call by value`, `call by reference` 두가지 방식으로 처리한다.

## 식별자 Identifier

![](../.gitbook/assets/IMG\_0364.PNG)

* `value` 는 메모리 주소에 값이 담겨있는 위치를 구분하기 위해 붙힌 이름
* `value` 식별자는 메모리 주소를 기억

## 자료구조/데이터 타입 Data Type

#### 원시타입 Primitive Type (call by value)

* Number
* String
* Boolean
* null
* undefined
* Symbol
* BigInt

원시 값은 변경 불가능(Immutable value)하다. 새로운 값을 새로운 메모리에 저장하여 해당 메모리 주소로 변경해서 값을 가져오기 때문에 원천 데이터가 변경되는 것이 아니다.

#### 객체/참조 타입 Object/Reference Type (call by reference)

* 원시타입을 제외한 나머지

`arr`은 재할당 불가능한 변수 값의 주소를 재할당할 수 없으나, 주소 안의 값은 변경할 수 있다.



## 변수 선언, 초기화 그리고 할당 Variables Hoisting

자바스크립트의 변수는 `var`, `let`, `const` 총 3가지 방법으로 선언할 수 있다. 변수를 선언해야하는 이유는 메모리 공간을 확보하는 것이고, 확보해야 데이터를 저장할 수 있기 때문이다. 이렇게 변수를 선언하게 되면 프로그램을 실행되기 전에 메모리를 효율적으로 관리하기 위하여 선언한 변수의 초기화를 진행하며 메모리 공간을 확보한다. 즉, 변수에 실제 값을 할당하기 전에 변수 `var`의 경우 `undefined` 값을 할당하여 메모리 공간을 확보한다. 이를 호이스팅 Hoisting이라고 하며 변수와 함수 등이 호이스팅 될 수 있다.

`var`, `let`, `const`는 각각 다른 방식으로 선언, 초기화 그리고 할당이 진행된다.&#x20;

### var

```javascript
console.log(foo); //undefined
var foo = 10;
foo = 20;
---------------------------------
//Hoisted
var foo; //declaration
foo = undefined; //initialization
console.log(foo); //undefined
foo = 10; //assignment
foo = 20; //re-assignment
```

`var`는 선언과 동시에 초기화가 일어난다. 그렇기 때문에 선언 전에 참조해도 호이스팅을 통해 초기화 일어나 `undefined` 값이 있기 때문에 에러가 발생하지 않는다. 또한 `var`는 재할당이 가능하다.

### let

```javascript
console.log(foo); //ReferenceError: foo is not defined
let foo = 10;
foo = 20;
-------------------------------------------------------
//Hoisted
let foo; //declaration
//TDZ scope start
console.log(foo); //ReferenceError: foo is not defined
//TDZ scope end
foo = 10; //assignment
foo = 20; //re-assignment
```

```javascript
console.log(foo); //undefined
let foo;
```

`let`은 작성된 코드에 따라 초기화와 할당이 분리될  수 있다. 선언만 한 경우 초기화가 같이 진행되어 `undefined` 값을 가진다. 그러나 할당까지 작성한 경우라면 호이스팅을 통해 선언은 일어나지만, 초기화와 할당이 동시에 일어나 값이 메모리에 할당되지 않아 에러가 발생한다. 해당 에러는 TDZ 에러로 `const`에서 발생하는 이유와 동일하다. 또한 `let`은 재할당이 가능하다.

### const

```javascript
console.log(foo); //ReferenceError: foo is not defined
const foo = 10;
foo = 20; //TypeError: Assignment to constant variable.
-------------------------------------------------------
//Hoisted
const foo; //declaration
//TDZ scope start
console.log(foo); //
//TDZ scope end
foo = 10; //assignment
foo = 20; //TypeError: Assignment to constant variable.
```

```javascript
console.log(foo); //SyntaxError: Missing initializer in const declaration
const foo; 
```

`const`는 선언과 동시에 값을 할당해야 한다. 호이스팅을 통해 선언은 일어나지만 초기화+할당이 진행되지 않았기 때문에 값이 메모리에 할당되지 않아 에러가 발생한다. 해당 에러는 TDZ 스코프에 포함되어 있기 때문에 발생하는 에러로 선언만 된 변수는 참조할 수 없기 때문에 에러가 발생한다. 또한 `const`는 재할당이 불가능하다.





<figure><img src="../.gitbook/assets/IMG_0336.PNG" alt=""><figcaption><p>Immutable value</p></figcaption></figure>



