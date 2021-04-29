# [210429] JavaScript - 배열(Array)

### 1. 배열이란?

`JavaScript`에서 `배열`이란 관련 있는 데이터를 하나의 변수에 할당하여 관리하기 위해 사용되는 데이터 타입이다. 

**배열의 두 가지 특징**

> 배열 내부의 데이터 타입이 서로 다를 수 있다
>
> 배열의 크기는 동적으로 변경될 수 있다



### 2. 생성

---

배열을 생성하는 방법은 2가지가 존재한다.

1. Array() 생성자 사용

```javascript
const array = new Array('a', 'b', 'c');
```

2. 배열 리터럴 대괄호([]) 사용

```javascript
const array = ['a', 'b', 'c'];
```





### 2. 메서드

---

- reverse - 반대로 정렬
- push & pop - 가장 뒤에 요소를 추가 또는 제거
- unshift & shift - 가장 앞에 요소를 추가 또는 제거
- includes - 특정 값이 존재하는지 판별 후 참/거짓 반환
- indexOf - 특정 값이 존재하는지 판별 후 인덱스 반환 (없으면 -1 반환)
- join - 모든 요소를 구분자를 이용하여 연결

<br>

**Array Helper Method** : 인자로 callback 함수를 받는 것이 특징

- forEach - 배열의 각 요소에 대해 콜백 함수를 한 번씩 실행(반환 값 없음)

```jsx
array.forEach((element, index, array) => {
	// do somethings
})
```

<br>

- map - 콜백 함수의 반환 값을 요소로 하는 새로운 배열 반환

```jsx
array.map((element, index, array) => {
	//do something
})
```

<br>

- filter 
  - 기존 배열의 요소들을 필터링할 때 유용
  - 콜백 함수의 반환 값이 참인 요소들만 모아서 새로운 배열을 반환

```jsx
array.filter((element, index, array) => {
  //do something
})
```

<br>

- reduce - 콜백 함수의 반환 값을 하나의 값(acc)에 누적 후 반환

```jsx
array.reduce((acc, element, index, array) => {
  // do something
}, initialValue)
```

<br>

- find - 콜백 함수의 반환 값이 참이면 해당 요소를 반환

<br>

- some - 배열의 요소 중 하나라도 판별함수를 통과하면 참을 반환

  ```
            - 빈 배열은 false 반환
  ```

<br>

- every - '' 모두 통과해야 참을 반환
