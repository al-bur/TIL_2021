# [210327] JavaScript - EventListener

### 1. Event, EventListener

---

- Event(이벤트) : 마우스 클릭, 움직임, 키보드 입력등의 물리적 요소
- Event Listner(이벤트 리스너) : 물리적 요소가 전달되어졌을 때 실행할 자바스크립트 코드

브라우저에서 일어나는 모든 일들은 이벤트라고 볼 수 있다. 이벤트가 일어나는 상황에서 브라우저에 특정한 움직임과 제어를 주고 싶을 때 이벤트 리스너를 사용해준다고 보면 된다.

<br>

### 2. 자주 쓰이는 Event 목록

---

| **이벤트 명** | **설명**                                 |
| ------------- | ---------------------------------------- |
| **change**    | 변동이 있을 때 발생                      |
| **click**     | 클릭 시 발생                             |
| **focus**     | 포커스를 얻었을 때 발생                  |
| **keydown**   | 키를 눌렀을 때 발생                      |
| **keyup**     | 키에서 손을 땟을 때 발생                 |
| **load**      | 로드가 완료 되었을 때 발생               |
| **mousedown** | 마우스를 클릭 했을 때 발생               |
| **mouseout**  | 마우스가 특정 객체 밖으로 나갔을 때 발생 |
| **mouseover** | 마우스가 특정 객체 위로 올려졌을 때 발생 |
| **mousemove** | 마우스가 움직였을 때 발생                |
| **mouseup**   | 마우스에서 손을 땟을 때 발생             |
| **select**    | option 태그 등에서 선택을 햇을 때 발생   |

<br>

### 3. EventListener 사용법

---

```javascript
# person 클래스를 가진 요소를 personId에 할당
const personId = document.querySelector('.person');

# 'click' 이벤트 발생 시 removeTitle 함수 실행
personId.addEventListener('click', removeTitle);

# removeTitle 실행
function removeTitle(){
    console.log(this.value)
}

```

1. 위처럼 제어를 하고 싶은 요소를 선택자를 활용해서 선택한다.

2. 원하는 이벤트 설정 후 이벤트가 발생하면 적용시킬 함수를 지정해준다.
