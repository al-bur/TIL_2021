# [210711] CS - Functional CSS

최근 화두로 떠오르고 있는 `Tailwind`의 베이스 개념인 `Functional CSS`에 대해서 알아보자

<br>

### Functional CSS란?

---

> Functional CSS (sometimes referred to as atomic CSS) is the practice of using small, immutable and explicitly named utility classes to construct components

외국 블로그의 글을 인용해보면, `Functional CSS`는 컴포넌트를 만들기 위해 조그마하고, 바뀌지 않고, 명확하게 이름 지어진 클래스들을 사용하는 것이라고 한다.

<br>

예시를 보면 더 쉽게 이해할 수 있을 것이다.

아래는 `navbar`라는 클래스에 `CSS`를 작성해준 것이다. 해당 클래스를 요소에 적용시켜주면 요소들을 모두 다 같은 요소로 만들어줄 수 있다.

<br>

```css
.navbar {
 font-size: 10px;
 margin-top: 5px;
 font-weight: bold;
 padding-left: 3px;
 background-color: yellow;
}
```

<br>

**만약 해당 `navbar`라는 클래스가 `A`, `B`, `C`라는 요소에서 쓰이고 있는 상황에서, 새로 업무를 맡은 직원이 오게 되었고 `B`의 배경색깔을 파란색으로 바꿔달라는 요청을 받았다고 해보자**

그렇게 된다면, 해당 직원은 `B`에 적용되어있는 클래스를 살펴보고 수정 방법을 찾아볼 것이다. 색을 변경하기 위해서  `navbar`라는 클래스를 직접 수정해버리면 `A`와 `C`까지 변경되버리는 요청되지 않은 작업까지 해버리게 된다.

<br>

아래는 `Functional CSS`의 예시이다.

```css
.ft-10 {
 font-size: 10px;
}

.mt-1 {
 margin-top: 5px;
}

.pl-1 {
 padding-left: 5px;
}

.bg-yellow {
 background-color: yellow;
}

.bg-blue {
 background-color: blue;
}
```

이렇게 `navbar` 클래스를 잘게 쪼개어서 각각의 클래스를 만들어주고 이를 활용해 스타일링을 하는 방식이다. 아까 같은 새로운 직원이 온 상황에서 만약 `Functional CSS`로 작업을 진행하고 있었다면, `bg-blue`라는 클래스로 교체해주면 빠르게 수정 작업을 진행할 수 있었을 것이다.

<br>

최근에 `Functional CSS`가 화두가 되고 있는데, 앞으로 어떻게 될지 궁금해진다..

