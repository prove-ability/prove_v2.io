---
title: useEffect🔥
date: 2020-01-30 23:01:84
category: Hooks🔥
draft: false
---

```js
useEffect(didUpdate);
```
>**라이프사이클 메서드를 대신할 수 있는 함수 🍎 기본적으로 동작은 모든 렌더링이 완료된 후에 수행됩니다만, 어떤 값이 변경되거나 변경되기 직전에 실행 가능하다**
## 기본형태
---
```js
useEffect(() => {
  console.log('렌더링 완료!');
});
```
> **componentDidMount, componentDidUpdate 를 합친 형태로 봐도 무방하다**  
> **정확히는 다른 타이밍에 동작하지만 지금은 넘어간다**
## Mounting 에만 실행하고 싶을 때
---
```js
useEffect(() => {
  console.log('렌더링 완료!');
}, []);
```
> **componentDidMount**  
> **2번째 파라미터에 빈 배열을 추가한다**
## Updating 에만 실행하고 싶을 때
---
```js
useEffect(() => {
  console.log(name);
}, [name]);
```
> **componentDidUpdate**
> **2번째 파라미터에 특정 값을 추가한 배열**
> **특정 값에 변화가 있다면 실행된다**
## 정리 함수
```js
useEffect(() => {
  const subscription = props.source.subscribe();
  return () => {
    // Clean up the subscription
    subscription.unsubscribe();
  };
});
```
> **마운트, 업데이트가 되기 직전에 실행하고 싶을 때 사용**
> **위의 예제는 매 갱신마다 새로운 구독이 생성**
```js
useEffect(
  () => {
    const subscription = props.source.subscribe();
    return () => {
      subscription.unsubscribe();
    };
  },
  [props.source],
);
```
> **특정 값(source)의 업데이트**  
> **만약 언마운트시 정리함수를 사용하고 싶다면 빈 배열을 추가**
***
#### 본 문서는 아래 문서를 참조하여 작성했습니다.
#### [useEffect doc](https://ko.reactjs.org/docs/hooks-reference.html#useeffect "useEffect doc link")