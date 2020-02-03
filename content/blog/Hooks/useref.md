---
title: useRef🔥
date: 2020-02-03 14:02:58
category: Hooks
draft: false
---

```js
const refContainer = useRef(initialValue);
```
> **함수형 컴포넌트에서 ref 를 쉽게 사용**
> **위의 경우 initialState 로 초기호된 변경 가능한 ref 객체를 반환**
## ref를 useRef로 설정하여 엘리먼트 참조하기
---
```js
function TextInputWithFocusButton() {
  const inputEl = useRef(null);
  const onButtonClick = () => {
    inputEl.current.focus();
  };
  return (
    <>
      <input ref={inputEl} type="text" />
      <button onClick={onButtonClick}>Focus the input</button>
    </>
  );
}
```
> **빈 배열을 사용하면 최초 렌더링시에만 함수를 생성한다**  

## 로컬 변수로 사용하기
---
```js
function RefSample() {
  const id = useRef(0);
  const setId = (n) => {
    id.current = n;
  }
  const printId = () => {
    console.log(id.current);
  }
  return (
    <div>
      refsample
    </div>
  );
};
```
> **로컬 변수는 렌더링에 영향을 끼치지 않는 값**
***
#### 본 문서는 아래 문서를 참조하여 작성했습니다.
#### [useRef doc](https://ko.reactjs.org/docs/hooks-reference.html#useref "useRef doc link")