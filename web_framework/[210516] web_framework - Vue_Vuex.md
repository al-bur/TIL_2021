# [210516] web_framework - Vue_Vuex

`Vue.js`에서의 기본적인 데이터 흐름은 `부모 컴포넌트`에서 `자식 컴포넌트`로 내려주는 단방향 흐름이라고 보면된다. 적은 수의 컴포넌트들로 구성되어 있는 웹 사이트라면 기존의 단방향 흐름 방식으로도 괜찮겠지만 프로젝트가 점점 커지다 보면 수많은 컴포넌트끼리 정보를 효율적으로 교환하고 싶어진다. 이럴 때 한 곳에 데이터를 모아서   컴포넌트들끼리 보다 편하게 데이터를 공유하고 사용할 수 있는 환경을 구축하기 위해 존재하는 것이 `Vuex`이다. 

<br>


### 1. Vuex란?

---

> Vuex는 Vue.js 애플리케이션에 대한 **상태 관리 패턴 + 라이브러리** 입니다. 애플리케이션의 모든 컴포넌트에 대한 중앙 집중식 저장소 역할을 하며 예측 가능한 방식으로 상태를 변경할 수 있습니다.

다른 말로 말하자면, 중앙 집중식 저장소를 운영하면서 데이터를 관리하고 이 데이터를 컴포넌트들이 유기적으로 사용하는 것이라고 보면된다. 해당 저장소를 vue.js에서는 `store`라고 한다. 

<br>

- Vuex 전체 흐름도

![vuex](https://vuex.vuejs.org/vuex.png)

<br>

### 2. 상태 관리 패턴

---

상태 관리란 여러 컴포넌트 간의 데이터 전달과 이벤트 통신을 한곳에서 관리하는 패턴을 의미합니다. 

상태 관리 구성요소는 크게 3가지가 있습니다.

- state: data (데이터)
- view: template (보여주는 것)
- actions: methods

```javascript
#store/index.js

new Vue({
  // state
  data() {
    return {
      counter: 0
    };
  },
  // view
  template: `
    <div>{{ counter }}</div>
  `,
  // actions
  methods: {
    increment() {
      this.counter++;
    }
  }
});

```

<br>

### 3. Vuex 기본 활용

---

먼저, npm을 이용하여 `Vuex`를 설치해줍니다.

```bash
npm install vuex
```

<br>

vuex를 등록할 js 파일 하나를 새로 생성합니다.

```javascript
// store.js
import Vue from "vue";
import Vuex from "vuex";

Vue.use(Vuex);

export const store = new Vuex.Store({
  // ...
});
```

<br>

프로젝트의 `main.js`로 가서 `store.js`를 불러와 등록

```javascript
// main.js
import Vue from "vue";
import App from "./App.vue";
// store.js를 불러오는 코드
import { store } from "./store";

new Vue({
  el: "#app",
  // 뷰 인스턴스의 store 속성에 연결
  store: store,
  render: h => h(App)
});
```

<br>

기본적인 설치와 파일 작성은 끝이고, store.js에서 state, mutations, actions, getters를 잘 활용하여 상태관리를 하면 된다!

