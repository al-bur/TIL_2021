# React - state에 관하여

React를 공부하면서, 알게 된 state에 관한 몇 가지 정보들을 정리해보고자 한다.

<br>

### 1. state를 변경하려고 하면 무조건 setState를 사용해서 변경해주어야함
---
이유는 state 값에 변경이 생긴다면 이 값을 토대로 render()를 호출해줘야 하는데 setState를 사용하면 React에서 자동으로 render function을 호출해줌

<br>

### 2. setState를 사용할 때 state안에 default값들을 선언할 필요는 없다.
---

```javascript
  class App extends React.Component{
    state = {
      isLoading: false,
    };
    componentDidMount() {
      setTimeout(() => {
        this.setState({ isLoading:true, book:true })
      }, 3000);
   }
```

{ book: true }라는 값이 state에 없어도 setState로 추가 가능

<br>

### 3. state가 필요없으면 class가 아닌 function component을 사용하면 된다.
---

하지만, 현재는 위의 말이 틀리게 되었다. react hook이라는 기능이 추가되면서, function component에서도 간편하게 state를 설정하고 사용해줄 수 있게 되었다.
