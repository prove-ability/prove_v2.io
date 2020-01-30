---
title: Hook 은 무었인가?
date: 2020-01-29 22:01:89
category: Hooks
draft: false
---
**Hook 은 함수형 컴포넌트에서 state 와 생명주기 기능을 연동할 수 있게 해주는 특별한 함수⭐**
> React v16.8, 
> React Native v0.59 부터 Hook을 지원한다   
> Hook 은 class 안에서는 동작하지 않는다

### Hook 을 사용할 땐 2가지 규칙을 지켜야 한다
---
**1. 반복문, 조건문 혹은 중첩된 함수 내에서 호출 금지**  
**2. React 함수 내에서만 Hook을 호출**

### 위에 2가지를 강제화 하기 위한 공식 플러그인 제공
---
```shell
npm install eslint-plugin-react-hooks --save-dev
```
```js
// ESLint 설정 파일
{
  "plugins": [
    // ...
    "react-hooks"
  ],
  "rules": {
    // ...
    "react-hooks/rules-of-hooks": "error", // Checks rules of Hooks
    "react-hooks/exhaustive-deps": "warn" // Checks effect dependencies
  }
}
```
> create react-app 은 기본적으로 포함이 되어 있음
***
#### 본 문서는 아래 문서를 참조하여 작성했습니다.
#### [hook doc](https://ko.reactjs.org/docs/hooks-intro.html#___gatsby "hook doc link")