# 배열 Array

## Array

배열은 동형(동일한 데이터 타입) 값을 저장할 수 있는 데이터 구조이다.&#x20;

## Array Method

### Array.prototype.every()

배열 내 모든 요소가 통과하는지에 따라 **Boolean** 반환

```javascript
const arr = [1, 2, 3, 4];
const result = arr.every((value) => value > 4); // false
```

### Array.prototype.filter()

주어진 함수의 테스트를 통과하는 모든 요소를 모아서 **새로운 배열**로 반환

```javascript
const arr = [1, 2, 3, 4];
const result = arr.filter(x => x < 3); // [1, 2]
```

### Array.prototype.forEach()

각 요소 별로 함수를 실행

```javascript
const arr = [1, 2, 3]
const result = arr.forEach((value) => console.log(value));
//1
//2
//3
```

### Array.prototype.join()

모든 요소를 연결해서 **하나의 문자열**을 반환

```javascript
const arr = ['Hello', 'I'm', 'Mochi.']
const result = arr.join(); //Hello,I'm,Mochi.
const result1 = arr.join(' '); //Hello I'm Mochi.
const result2 = arr.join('-'); //Hello-I'm-Mochi.
```

### Array.prototype.indexOf()

배열 내에서 특정 요소를 찾아 검색된 **첫번째 인덱스**를 반환

```javascript
const arr = ['apple', 'banana', 'orange']
const result = arr.indexOf('banana', 1); //1
const result2 = arr.indexOf('a'); // -1 찾을 수 없는 경우
```

### Array.prototype.map()

배열 내의 모든 요소를 각각에 주어진 함수를 호출한 결과를 모아서 **새로운 배열** 반환

```javascript
const arr = [1, 2, 3, 4];
const result = arr.map(x => x * x); // [1, 4, 9, 16]
```

### Array.prototype.push()

인수로 받은 모든 값을 원본 배열 마지막 요소로 추가해서 **변경된 Length**를 반환

```javascript
const arr = [1, 2];
const result = arr.push(3, 4); //4
console.log(arr) // [1, 2, 3, 4]
```

#### \*Length

Length를 이용해서 배열에 요소를 추가할 수 있음

```javascript
const arr = [1, 2];
arr[arr.length] = [3, 4];
console.log(arr) // [1, 2, 3, 4]
```

#### \*Spread

```javascript
const arr = [1, 2];
const result = [...arr, 3, 4]; // [1, 2, 3, 4]
```

### Array.prototype.pop()

원본 배열의 마지막 요소를 원본 배열에서 직접 제거하고 **제거한 요소**를 반환

\*원본 배열이 빈 배열이면 `undefined`를 반환

```javascript
const arr = [1, 2];
let result = arr.pop(); // 2
console.log(arr) // [1]
```

### Array.prototype.unshift()

인수로 전달받은 모든 값을 원본 배열 가장 처음에 추가하고 **변경된 Length** 반환

```javascript
const arr = [1, 2];
const result = arr.unshift(-1, 0); // 4
console.log(arr) // [-1, 0, 1, 2]
```

#### \*Spread

```javascript
const arr = [1, 2];
const result = [-1, 0, ...arr]; // [-1, 0, 1, 2]
```

### Array.prototype.shift()

원본 배열에서 첫 번째 요소를 제거하고 **제거한 요소**를 반환

\*원본 배열이 빈 배열이면 `undefined`를 반환

```javascript
const arr = [1, 2];
let result = arr.shift(); // 1
console.log(arr) // [2]
```

### Array.prototype.concat()

concat에 넣는 값은 원본 배열에 마지막에 추가 (배열인 경우 해체됨) **새로운 배열**로 반환

```javascript
const arr = [1, 2];
const arr2 = [3, 4];
const result = arr.concat(arr2); // [1, 2, 3, 4]
console.log(arr, arr2) // [1, 2] [3, 4]
```

#### \*Spread

```javascript
const arr = [1, 2];
const result = [...arr, 3, 4]; // [1, 2, 3, 4]
```

### Array.prototype.splice()

직접 원본 배열의 중간 요소를 추가/제거하고 **제거한 요소**를 배열로 반환

```javascript
const arr = [1, 2];
const arr2 = [2, 3, 4];
let result = arr.splice(1, 1, arr2, 5); // (start, deleteCount opt, items opt)
console.log(result) // [2]
console.log(arr) // [1, 2, 3, 4, 5]
```

`-n`인 경우 배열의 마지막 부터 카운트

```javascript
const arr = [1, 2, 3];
let result = arr.splice(1); // [2, 3]
```

### Array.prototype.slice()

인수로 전달된 범위의 요소들을 복사해서 **새로운 배열**로 반환

```javascript
const arr = [1, 2, 3];
let result = arr.slice(0, 1); // (start, end opt)
console.log(result) // [1]
```

```javascript
const arr = [{x:1, y:2}]
const arr2 = arr.slice();
console.log(arr.x === arr2.x) // true
console.log(arr === arr2) // false
```
