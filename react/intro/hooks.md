# Hooks

render props, 고차 컴포넌트를 통해 컴포넌트 재사용?

context, 고차 컴포넌트, render props 등을 통해 wrapper hell이 발생?



\-> Hook을 사용하면 컴포넌트로부터 상태 관련 로직을 추상화하여 테스트 및 재사용 가능

\-> Hook은 계층의 변화 없이 상태 관련 로직을 재사용 가능



Class 컴포넌트의 경우 각 생명주기 메서드에 관련 없는 로직이 포함될 수 있음

\-> 하나의 로직을 만들고 싶은데 각 생명주기 별 메서드는 1개 밖에 사용할 수 없고 이 안에 관련없는 로직도 포함되어 있으니 사이드 이펙트나 재사용하기가 어렵다?

\-> 상태 관련 로직은 묶여있기 때문에 컴포넌트들을 작게 분리하기가 어렵고 테스트도 어렵다

```jsx
import React, { Component } from 'react';

class Counter extends Component {
    state = {counter: 0}
    
    componentWillMount() {
        //...
    }
    
    componentDidMount() {
        //...
    }
    
    onIncrement = () => {
    this.setState({
        counter: this.state.counter + 1
    });
    }

    onDecrement = () => {
        this.setState({
            cunter: this.state.counter - 1
        });
    }

    render() {
        return (
            <div>
                <p>{this.state.counter}</p>
                <button onClick={this.onIncrement}>+</button>
                <button onClick={this.onDecrement}>-</button>
            </div>
        )
    }
}

export default Counter;
```



그래서 생명주기 메서드 기반으로 쪼개는 것보다 Hooks를 통해 작은 로직을 담은 컴포넌트를 묶을 수 있도록 하기 위해 탄생함



Class는 미리 컴파일하는 방식에 적합하지 않을 수 있다

Hooks를 통해 Class 없이도 React 기능을 사용할 수 있게됨







