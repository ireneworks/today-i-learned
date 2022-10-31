# props

props는 변하지 않는 데이터(Immutable data)이다.

### 부모 컴포넌트

```jsx
import Mochi from './Mochi.js';

function World() {
    return(
        <Mochi name="김모찌" />
    )
}
```

### 자식 컴포넌트

```jsx
import React from 'react';

function Mochi(props) => {
    return ((props.name)+"입니다."
    );
    }

export default Mochi;
```

```jsx
import React from 'react';
```
