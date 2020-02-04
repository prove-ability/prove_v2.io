---
title: useState🔥
date: 2020-01-30 21:01:27
category: Hooks🔥
draft: false
---

```js
const [state, setState] = useState(initialState);
```
>**상태 값과 그 값을 변경하는 함수를 반환한다🍎 최초 렌더링시 initialState 의 값으로 state 초기화**
```js
setState(newState);
```
> **setState 함수는 state 를 갱신할 때 사용**
### 예제
---
```js
const initialState = {
	value: 0
};

function Counter() {
  const [count, setCount] = useState(initialState);
  return (
    <>
      Count: {count}
      <button onClick={() => setCount(count - 1)}>-</button>
      <button onClick={() => setCount(count + 1)}>+</button>
    </>
  );
}
```
> setCount 함수가 동일한 값을 반환한다면 리렌더링을 건너뛴다  
이때 비교는 Object.is() 사용한다
***
#### 본 문서는 아래 문서를 참조하여 작성했습니다.
#### [useState doc](https://ko.reactjs.org/docs/hooks-reference.html#usestate "useState doc link")