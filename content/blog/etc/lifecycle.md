---
title: lifesycle⭐
date: 2020-02-05 21:02:68
category: etc⭐
draft: false
---

# constructor

```js
constructor(props);
```

> **React.Component 를 사용하여 생성한 클래스형 컴포넌트는 생명주시 메서드를 사용할 수 있다** > **그 중 constructor 는 this.state 초기화하는데 사용하며 이벤트 처리 메서드에 바인딩 처리를 도와줌**

### state 초기화

```js
constructor(props) {
  super(props);
  // 여기서 this.setState()를 호출하면 안 됩니다!
  this.state = { counter: 0 };
  this.handleClick = this.handleClick.bind(this);
}
```

> **절대 state 에 props 를 복사해서는 안된다** > **아래 예시에서 props 가 변경되어도 state 에 반영되지 않는다**

```js
constructor(props) {
 super(props);
 // 이렇게 하지 마세요!
 this.state = { color: props.color };
}
```

### 이벤트 메서드 바인딩

```js
class Toggle extends React.Component {
  constructor(props) {
    super(props);
    this.state = { isToggleOn: true };

    // 콜백에서 `this`가 작동하려면 아래와 같이 바인딩 해주어야 합니다.
    this.handleClick = this.handleClick.bind(this);
  }

  handleClick() {
    this.setState(state => ({
      isToggleOn: !state.isToggleOn,
    }));
  }

  render() {
    return (
      <button onClick={this.handleClick}>
        {this.state.isToggleOn ? 'ON' : 'OFF'}
      </button>
    );
  }
}

ReactDOM.render(<Toggle />, document.getElementById('root'));
```

---

#### 본 문서는 아래 문서를 참조하여 작성했습니다.

#### [constructor doc](https://ko.reactjs.org/docs/react-component.html#constructor 'constructor doc link')
