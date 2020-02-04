---
title: useContext🔥
date: 2020-01-31 12:01:89
category: Hooks🔥
draft: false
---

>**전역적으로 사용이 필요한 state 를 위해 사용한다 🍎 보통 로그인한 유저 정보, 테마, 언어 를 위해 사용한다**
## useContext 를 사용하지 않은 형태
---
```js
class App extends React.Component {
  render() {
    return <Toolbar theme="dark" />;
  }
}

function Toolbar(props) {
  return (
    <div>
      <ThemedButton theme={props.theme} />
    </div>
  );
}

class ThemedButton extends React.Component {
  render() {
    return <Button theme={this.props.theme} />;
  }
}
```
> **App - Toolbar - ThemedButton**  
> **App 에 있는 테마 정보를 ThemedButton 전달하고자 Toolbar 를 거쳐야 한다**
## Mounting 에만 실행하고 싶을 때
---
```js
const ThemeContext = React.createContext('light');

class App extends React.Component {
  render() {
    return (
      <ThemeContext.Provider value="dark">
        <Toolbar />
      </ThemeContext.Provider>
    );
  }
}

function Toolbar(props) {
  return (
    <div>
      <ThemedButton />
    </div>
  );
}

class ThemedButton extends React.Component {
  static contextType = ThemeContext;
  render() {
    return <Button theme={this.context} />;
  }
}
```
> **Toolbar 를 거치지 않고 전달이 가능하다**  

## API
---
### **React.createContext**
```js
const MyContext = React.createContext(/* value */);
```
> **전역적으로 사용하는 value 를 context객체로 생성**
### **Context.Provider**
```js
<MyContext.Provider value={/* value */}>
```
> **Provider는 context를 구독하는 컴포넌트들에게 context의 변화를 알리는 역할**
> **상위 컴포넌트에서 Provider 를 설정하고 하위 컴포넌트에서 구독한다 🍎 구독한 컴포넌트는 Provider 의 value 가 변경되면 리렌더링 된다**
### **Class.contextType**
```js
class MyClass extends React.Component {
  componentDidMount() {
    let value = this.context;
    /* MyContext의 값을 이용한 코드 */
  }
  componentDidUpdate() {
    let value = this.context;
    /* ... */
  }
  componentWillUnmount() {
    let value = this.context;
    /* ... */
  }
  render() {
    let value = this.context;
    /* ... */
  }
}
MyClass.contextType = MyContext;
```
> **장 가까운 Provider를 찾아 그 값을 읽을 수 있다 🍎 해당 API 는 하나의 context 만 구독이 가능하다**
### **Context.Consumer**
```js
<MyContext.Consumer>
  {value => /* context 값을 이용한 렌더링 */}
</MyContext.Consumer>
```
> **함수 컴포넌트안에서 context를 읽기 위해서 사용**
***
#### 본 문서는 아래 문서를 참조하여 작성했습니다.
#### [usecontext doc](https://ko.reactjs.org/docs/hooks-reference.html#usecontext "usecontext doc link")