# import & export

### import

```jsx
//기본
import Example from './Example.js';

//export 할 때 default가 없으면 중괄호가 필수
import {Example} from './Example.js';

import React, {Component} from 'react';

//node_modules에 설치된 모듈을 불러올 때는 경로 지정 필요없음
import Example from 'Example';

//모듈 전체의 사이드 이펙트만 가져온다는데 
import './Example.js';
```

### export

```jsx
const coffee = function (i) {
   let sum = i + 2 
};

const example = 2;


export default coffee;
export {example};
export const foo = "HI";
```

```jsx
import coffee.sum, {example, foo} from './example';
```

`default`를 쓰면 기본적으로 보낼 것을 정한다. 파일에서 한번만 쓸 수 있다.
