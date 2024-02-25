---
description: stack/queue
---

# 올바른 괄호 Valid Parentheses

```javascript
// 문자열 str가 주어졌을때 괄호가 제대로 열리고 닫혀있는지를 출력해라
// 문자열은 ( ) 두가지만 주어지며 반드시 열리고 닫혀야 한다.
// 문자열은 100,000 이하의 자연수이다.

'()()' // true
'(())()' // true
')()(' // false
'(()('  // false
```

한쌍으로 구분이 되는지 보려고 했으나 이는 `(())()` 를 만족시키지 못하기 때문에 제대로 된 접근이 아니였다. 기존에 풀어봤던 후위연산식 문제에서 괄호도 stack으로 처리하는 방법을 대입해보다가 [블로그](https://jaejade.tistory.com/133)에서 힌트를 얻었다.

가장 중요한 점은 **`stack`** 문제라는 것이고, stack은 LIFO(Last in First Out) 이다.

```javascript
function solution(str) {
    // 닫힘이 먼저 나오면 무조건 false 이므로 먼저 분기처리
    if(str[0] !== '(') {
        return false;
    }
    
    // stack에서 중첩 괄호 체크
    const stack = [];
    for(let i of str){
        // 열림이면 push
        if(i === '(') {
            stack.push(i);
        } else {
            // 닫힘이면 열림을 pop
            stack.pop();
        }
    }
    // 만약 쌍이 안 맞아서 남아있다면 false
    return stack.length === 0;
}
```

```javascript
// stack log

solution('(())()');

['(']
['(', '(']
['(']
[]
['(']
[]
```

<div align="left">

<figure><img src="../.gitbook/assets/스크린샷 2024-02-25 오후 5.15.22.png" alt="" width="164"><figcaption></figcaption></figure>

</div>

시간 복잡도를 계산해본다면 for 문 도는 것이 가장 큰 작업이기에 O(n)으로 생각된다.
