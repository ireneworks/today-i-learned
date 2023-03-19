# Find longest substring without repeating characters

연속되지 않는 문자열중에 가장 긴 문자열의 개수를 구하라

```
Input: "abcabcbb" / Output: 3
Answer: "abc", 3

Input: "bbbbb" / Output: 1
Answer: "b", 1

Input: "pwwkew" / Output: 3
Answer: "wke", 3
```



```javascript
function answer(str) {
    let temporaryString = '';
    let maxLength = 0;
    
    for(let i = 0; i < str.length; i++) {
        const indexOf = temporaryString.indexOf(str[i]);
        if(indexOf > -1) {
            temporaryString = temporaryString.slice(indexOf + 1).concat(str[i]);
        } else {
            temporaryString = temporaryString.concat(str[i]);
            maxLength = Math.max(temporaryString.length, maxLength);
        }
    }
    return maxLength;
}

//
```
