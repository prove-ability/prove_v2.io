---
title: usecallback🔥
date: 2020-02-02 15:02:52
category: Hooks
draft: false
---

```js
const memoizedCallback = useCallback(
  () => {
    doSomething(a, b);
  },
  [a, b],
);
```
> **보통 컴포넌트의 성능 최적화를 위해 사용한다**  
> **위에 예시에서 useCallback 를 사용하지 않는다면 컴포넌트가 리렌더링 될 때마다 새로 생성이 된다 🍎 이 부분이 문제를 일으키지는 않지만 렌더링이 자주 발생한다면 성능을 저하시킬 수 있다**  
> **함수에서 의존해야 하는 상태가 있다면 2번째 파라미터에 배열을 통해 전달한다**  
> **위의 함수는 의존성이 변경되었을 때에만 변경된다.**
## 의존해야 하는 상태가 없는 경우
---
```js
const memoizedCallback = useCallback(
  () => {
    console.log('hello world!');
  }, 
  []
)
```
> **빈 배열을 사용하면 최초 렌더링시에만 함수를 생성한다**  


***
#### 본 문서는 아래 문서를 참조하여 작성했습니다.
#### [useCallback doc](https://ko.reactjs.org/docs/hooks-reference.html#usecallback "useCallback doc link")