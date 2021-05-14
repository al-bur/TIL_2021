# [210514] web_framework - Vue_디렉티브

- Vue.js에서 쓰이는 문법

- v-접두사가 있는 특수 속성

- 종류

  - v-text : innerText와 동일한 기능을 수행하며 태그를 인코딩하여 문자그대로 보여줌
  - v-html :  엘리먼트의 innerHTML을 업데이트 (XSS 공격에 취약할 수 있음) // 절대 사용금지
  - v-if: if 조건문을 구현함
  - v-for : for 반복문을 구현함 , key값 필수
  - v-on : 엘리먼트에 이벤트 리스너를 연결

  - v-bind : HTML요소의 속성에 Vue의 상태 데이터를 값으로 할당

  - v-model : 양방향 바인딩

