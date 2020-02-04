---
title: strictMode⭐
date: 2020-02-04 17:02:88
category: etc⭐
draft: false
---

## 엄격모드란

```js {7,12}
import React from 'react';

function ExampleApplication() {
  return (
    <div>
      <Header />
      <React.StrictMode>
        <div>
          <ComponentOne />
          <ComponentTwo />
        </div>
      </React.StrictMode>
      <Footer />
    </div>
  );
}
```

> **애플리케이션 내의 잠재적인 문제를 알아내기 위한 도구 🍎 Fragment와 같이 UI를 렌더링하지 않으며, 자손들에 대한 부가적인 검사와 경고를 활성화**

---

**개발 환경에서 아래와 같은 문제를 찾아준다**

1. **안전하지 않은 생명주기를 사용하는 컴포넌트 발견**

#### 발견된 컴포넌트는 경고 로그를 출력한다

2. 레거시 문자열 ref 사용에 대한 경고

#### 기존의 문자열 ref API 보다는 createRef, 콜백 ref 를 권장한다

3. 권장되지 않는 findDOMNode 사용에 대한 경고

#### findDOMNode 보다는 ref 속성 사용 권장

4. 예상치 못한 부작용 검사

#### 이중으로 호출되는 생명주기 메서드 검사

5. 레거시 context API 검사

#### 구버전 context API 마이그레이션 권장

> **Strict 모드는 개발 모드에서만 활성화되기 때문에, 프로덕션 빌드에는 영향을 끼치지 않는다.**

---

#### 본 문서는 아래 문서를 참조하여 작성했습니다.

#### [StrictMode doc](https://ko.reactjs.org/docs/strict-mode.html#identifying-unsafe-lifecycles 'StrictMode doc link')
