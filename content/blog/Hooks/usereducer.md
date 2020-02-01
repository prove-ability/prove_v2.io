---
title: useReducer🔥
date: 2020-02-01 14:02:52
category: Hooks
draft: false
---

```js
const [state, dispatch] = useReducer(reducer, initialArg, init);
```
>**다수의 하윗값을 포함하는 복잡한 정적 로직을 만드는 경우나 다음 state가 이전 state에 의존적인 경우에 보통 useState보다 useReducer를 선호 🍎**
---
## 사용 예시
```js
const initialState = {
  count: 0
};

function reducer(state, action) {
  switch (action.type) {
    case 'increment':
      return {count: state.count + 1};
    case 'decrement':
      return {count: state.count - 1};
    default:
      throw new Error();
  }
}

function Counter() {
  const [state, dispatch] = useReducer(reducer, initialState);
  return (
    <>
      Count: {state.count}
      <button onClick={() => dispatch({type: 'decrement'})}>-</button>
      <button onClick={() => dispatch({type: 'increment'})}>+</button>
    </>
  );
}

```
> **일반적인 경우 위와 같이 사용한다**
---
## initialState 의 변경이 필요한 경우
```js
function init(initialCount) {
  return {count: initialCount};
}

function reducer(state, action) {
  switch (action.type) {
    case 'increment':
      return {count: state.count + 1};
    case 'decrement':
      return {count: state.count - 1};
    case 'reset':
      return init(action.payload);
    default:
      throw new Error();
  }
}

function Counter({initialCount}) {
  const [state, dispatch] = useReducer(reducer, initialCount, init);
  return (
    <>
      Count: {state.count}
      <button
        onClick={() => dispatch({type: 'reset', payload: initialCount})}>
        Reset
      </button>
      <button onClick={() => dispatch({type: 'decrement'})}>-</button>
      <button onClick={() => dispatch({type: 'increment'})}>+</button>
    </>
  );
}
```
> **3번째 파라미터에 init 을 사용하면 나중에 state를 재설정하는 데에도 유용하다**
---
#### 본 문서는 아래 문서를 참조하여 작성했습니다.
#### [useReducer doc](https://ko.reactjs.org/docs/hooks-reference.html#usereducer "usereducer doc link")