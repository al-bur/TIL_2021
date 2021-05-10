# [210510] web_framework - Vue CLI

오늘은 저번에 `Vue.js`에 대해서 공부해본 것에 이어서 `Vue CLI`에 대해서 공부를 해보았습니다!

<br>

### 1. Vue CLI란?

---

먼저, Vue CLI는 기본 `Vue` 개발 환경을 설정해주는 도구이고  `Vue`를 활용해서 빠르게 개발을 하고 싶을때 Vue CLI을 사용한다고 생각하면 됩니다. 

> CLI(Command Line Interface)는 명령줄 인터페이스로 텍스트 터미널을 통해 사용자와 컴퓨터가 상호 작용하는 방식을 뜻한다. (출처- 위키백과)



Vue CLI를 활용해서 할 수 있는 것들을 살펴보면 (출처 - https://uxgjs.tistory.com/136)

- 새로운 Vue 프로젝트 생성 - 몇 가지 기본 골격을 선택하여 `Vue` 프로젝트를 빠르게 생성할 수 있음
- Vue 플러그인 설치/삭제 - 다양한 `Vue` 플러그인들을 추가하거나 삭제
- Vue.config.js 설정 - 웹팩의 구성에 대해 `vue.config.js`로 오버라이딩하여 추가 설정 가능
- Vue GUI 도구 사용 - cli가 낯선 개발자를 위해 GUI형태로도 도구를 제공

<br>

### 2. Vue CLI 설치

---

`npm`이 미리 설치되어 있어야 합니다.

> npm - JavaScript 프로그래밍 언어를 위한 패키지 관리자


```vue
npm install -g @vue/cli
```

<br>

### 3. Vue CLI로 프로젝트 생성

---

```vue
vue create 프로젝트명
```

<br>

### 비고

---

앞으로, 자주 쓰게 될 `Vue CLI`에 대해서 알아보았습니다. 추가적으로, 추후에 `webpack`에 대해서 공부해보겠습니다

