# 후위 표현법 Postfix notation

```javascript
function solution(value) {
    const str = value.replace(/ /g, "").split('');
    let postfix = "";
    const operatorStack = [];
    const operatorPriority = {
        '(': 0,
        '+': 1,
        '-': 1,
        '*': 2,
        '/': 2,

    };

    for (let i = 0; i < str.length; i++) {
        if (!isNaN(+str[i])) {
            postfix += str[i];

        } else {
            if (!operatorStack.length) {
                operatorStack.push(str[i]);

            } else {
                if (operatorPriority[str[i]] >= operatorPriority[operatorStack[operatorStack.length - 1]]) {
                    operatorStack.push(str[i]);
                } else {
                    while (operatorStack[operatorStack.length - 1] === '(' || operatorStack.length) {
                        postfix += operatorStack.pop();
                    };
                    if(operatorStack[operatorStack.length - 1] === '(') {
                        delete operatorStack[operatorStack.length - 1];
                    }
                    operatorStack.push(str[i]);
                }
            }
        }

    }
    while(operatorStack.length) {
        postfix += operatorStack.pop();
    }

    const calculateStack = [];


    for(let i = 0; i < postfix.length; i++) {
        if(!isNaN(+postfix[i])) {
            calculateStack.push(+postfix[i])
        }
        else {
            const right = calculateStack.pop();
            const left = calculateStack.pop();

            switch (postfix[i]) {
                case "+":
                    calculateStack[calculateStack.length] = left + right;
                    break
                case "-":
                    calculateStack[calculateStack.length] = left - right;
                    break
                case "*":
                    calculateStack[calculateStack.length] = Math.ceil(left * right);
                    break
                case "/":
                    calculateStack[calculateStack.length] = Math.ceil(left / right);
                    break
            }

        }

    }
    return calculateStack[0];
}


console.log(solution("3 * (3 - 1) + 2") === 8)

// console.log(solution("1 + 1") === 2)
// console.log(solution("4/2+2") === 4)
// console.log(solution("3/2+1") === 3)
// console.log(solution(" 2+3*1  -1 ") === 4)
// console.log(solution("2+ 3* 1") === 5)
```
