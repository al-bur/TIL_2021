# [always] Javascript 개념 한 줄 정리

### 변수
---
- 변수 : 하나의 값을 저장하기 위해 확보한 메모리 공간 자체 또는 그 메모리 공간을 식별하기 위해 붙인 이름. 프로그래밍 언어에서 값을 저장하고 참조하는 메커니즘으로, 값의 위치를 가리키는 상징적인 이름.
- 식별자 : 어떤 값을 구별해서 식별해낼 수 있는 고유한 이름. 식별자는 값이 아니라 메모리 주소를 기억하고 있다.
- 호이스팅 : 선언문이 코드의 선두로 끌어 올려진 것처럼 동작하는 자바스크립트 고유의 특징. *키워드를 사용해서 선언하는 모든 식별자(변수, 함수, 클래스등)는 호이스팅된다.
- 초기화 : 변수가 선언된 이후 최초로 값을 할당하는 것. 값을 저장하기 위한 메모리 공간을 확보하고 암묵적으로 undefined를 할당해 초기화한다.
- 키워드 : 자바스크립트 코드를 해석하고 실행하는 자바스크립트 엔진이 동작을 규정한 일종의 명령어. 엔진은 키워드를 만나면 자신이 수행해야 할 약속된 동작을 수행
- 변수 선언 :   변수 선언이란 변수를 생성하는 것 .변수 선언은 소스코드가 순차적으로 실행되는 시점인 런타임 이전에 먼저 실행. 변수 이름을 등록해서 자바스크립트 엔진에 변수의 존재를 알림.
- 할당 : 변수에 값을 저장하는 것. 값의 할당은 소스코드가 순차적으로 실행되는 시점인 런타임에 실행
- 재할당 : 이미 값이 할당되어 있는 변수에 새로운 값을 또다시 할당하는 것
- 상수 : 단 한번만 할당할 수 있는 변수. 값을 재할당 할 수 없어서 변수에 저장된 값을 변경할 수 없다면 변수가 아니라 상수이다. 상수도 값을 저장하기 위한 메모리 공간이 필요하므로 변수라고 할 수 있다.
- 가비지 콜렉터 : 애플리케이션이 할당한 메모리 공간을 주기적으로 검사하여 더 이상 사용되지 않는 메모리를 해제하는 기능
- 리터럴: 사람이 이해할 수 있는 문자 또는 약속된 기호를 사용해 값을 생성하는 표기 방식
- 연산자 : 연산자는 하나 이상의 표현식을 대상으로 산술, 할당, 비교, 논리, 타입, 지수 연산등을 수행해 하나의 값을 만든다. (ex. 산술 연산자, 할당 연산자, 비교 연산자 등등)
- 바인딩 : 식별자와 값을 연결하는 과정. ex) 변수 선언은 변수 이름(식별자)과 확보된 메모리 공간의 주소를 바인딩하는 것


<br>


### 스코프
---

- 스코프(유효범위) : 식별자가 유효한 범위. 모든 식별자(변수 이름, 함수 이름, 클래스 이름 등)는 자신이 선언된 위치에 의해 다른 코드가 식별자 자신을 참조할 수 있는 유효범위가 결정된다. 이를 스코프라 한다. 
- 스코프 체인 : 스코프가 계층적으로 연결된 것 (ex. 최상위 스코프인 전역 스코프, 전역에서 선언된 outer 함수의 지역 스코프, outer 함수 내부에서 선언된 inner 함수의 지역 스코프). 식별자 검색을 위한 
- 블록 레벨 스코프 : 모든 코드 블록(if, for, while, try/catch등)이 지역 스코프를 만드는 특성
- 함수 레벨 스코프 : 함수의 코드 블록(함수 몸체)만을 지역 스코프로 인정하는 특성 (ex. var 키워드)
- 동적 스코프 : 함수를 어디서 호출했는지에 따라 함수의 상위 스코프를 결정
- 정적 스코프(렉시컬 스코프) : 함수를 어디서 정의했는지에 따라 함수의 상위 스코프를 결정
- 전역 객체 : 코드가 실행되기 이전 단계에 자바스크립트 엔진에 의해 어떤 객체보다도 먼저 생성되는 특수한 객체. (ex. window 객체)
<br>

### 타입
---
- 타입 : 값의 종류
- 원시 타입: 원시 타입의 값은 변경 불가능한 값이다. 반면, 객체 타입의 값은 변경 가능한 값
- 객체 : 상태 데이터와 동작을 하나의 논리적인 단의로 묶은 복합적인 자료구조. 0개 이상의 프로퍼티로 구성된 집합
- 프로퍼티 : 객체의 상태를 나타내는 값(data) ,프로퍼티는 키와 값으로 구성되고 객체는 프로퍼티의 집합
- 메서드 : 프로퍼티(data)를 참조하고 조작할 수 있는 동작, 프로퍼티 값이 함수일 경우, 일반 함수와 구분하기 위해 메서드라 부른다.
- 유사배열객체 : 마치 배열처럼 인덱스로 프로퍼티 값에 접근할 수 있고 length 프로퍼티를 갖는 객체
- this : 객체 자신의 프로퍼티나 메서드를 참조하기 위한 자기 참조 변수다. this가 가리키는 값, 즉 this 바인딩은 함수 호출 방식에 따라 동적으로 결정된다. (일반 함수로서 호출 - 전역객체 // 메서드로서의 호출 - 메서드를 호출한 객체 // 생성자 함수로서 호출 -> 생성자 함수가 (미래에) 생설할 인스턴스)

<br>

### 문(statement)와 표현식(expression)
---

- 값 : 식(표현식_expression)이 평가 되어 생성된 결과
- 평가 : 식을 해석해서 값을 생성하거나 참조하는 것
- 문(statement) : 프로그램을 구성하는 기본 단위이자 최소 실행 단위. 문의 집합으로 이루어진 것이 프로그램. 문은 여러 토큰으로 구성된다.
- 토큰 : 문법적인 의미를 가지며, 문법적으로 더 이상 나눌 수 없는 코드의 기본 요소 (ex. 키워드, 식별자, 연산자등등)
- 표현식(expression) : 값으로 평가될 수 있는 문(statement)이다. 즉, 표현식이 평가되면 새로운 값을 생성하거나 기존 값을 참조한다. (ex. var score = 50 + 50)
- 블록문 : 0개 이상의 문을 중괄호로 묶은 것으로, 코드 블록 또는 블록이라고 부르기도 한다. 블록문을 하나의 실행 단위로 취급
- 제어문 : 조건에 따라 코드 블록을 실행(조건문)하거나 반복 실행(반복문)할 때 사용한다.
- 조건문 : 주어진 조건식의 평가 결과에 따라 코드 블록(블록문)의 실행을 결정한다. 조건식은 불리언 값으로 평가될 수 있는 표현식이다.

<br>

### 함수
----
- 함수 : 프로그래밍 언어의 함수는 일련의 과정을 문(statement)으로 구현하고 코드 블록으로 감싸서 하나의 실행 단위로 정의한 것
- 함수 정의 : 함수 정의란 함수를 호출하기 이전에 인수를 전달받을 매개변수와 실행할 문들, 그리고 반환할 값을 지정하는 것, 정의된 함수는 자바스크립트 엔진에 의해 평가되어 함수 객체가 된다.
- 함수 호출 : 인수(argument)를 매개변수를 통해 함수에 전달하면서 함수의 실행을 명시적으로 지시하는 것
- 재귀 호출: 함수가 자기 자신을 호출하는 것
- 즉시 실행 함수 : 함수 정의와 동시에 즉시 호출되는 함수
- 콜백함수 : 함수의 매개변수를 통해 다른 함수의 내부로 전달되는 함수
- 순수함수 : 외부 상태를 변경하지 않고 외부 상태에 의존하지도 않는 함수
- 함수형 프로그래밍 : 순수 함수를 통해 부수 효과를 최대한 억제하여 오류를 피하고 프로그램의 안정성을 높이려는 프로그래밍 패러다임
- 생성자 함수 : new 연산자와 함께 호출하여 객체(인스턴스)를 생성하는 함수
- 인스턴스 : 생성자 함수에 의해 생성된 객체

<br>

### 프로퍼티 어트리뷰트
---

- 데이터 프로퍼티 : 키와 값으로 구성된 일반적인 프로퍼티. 
- 접근자 프로퍼티 : 자체적으로는 값을 갖지 않고 다른 데이터 프로퍼티의 값을 읽거나 저장할 때 호출되는 접근자 함수로 구성된 프로퍼티.

<br>

### 프로토타입
---

- 프로토타입 : 어떤 객체의 상위(부모) 객체의 역할을 하는 객체이다. 프로토타입은 하위(자식) 객체에게 자신의 프로퍼티와 메서드를 상속한다. 프로토타입과 생성자 함수는 단독으로 존재할 수 없고 언제나 쌍으로 존재한다.
- 프로토타입 체인 : 객체의 프로퍼티에 접근하려고 할 때 해당 객체에 접근하려는 프로퍼티가 없다면 [[Prototype]] 내부 슬롯의 참조를 따라 자신의 부모 역할을 하는 프로토타입의 프로퍼티를 순차적으로 검색하는 것. 프로토타입이 단방향 링크드 리스트 형태로 연결되어 있는 상속 구조. 모든 객체는 프로토타입의 계층 구조인 프로토타입 체인에 묶여있다. 상속과 프로퍼티 검색을 위한 
- 객체지향 프로그래밍 : 프로그램을 명령어 또는 함수의 목록으로 보는 전통적인 명령형 프로그래밍의 절차지향적 관점에서 벗어나 여러 개의 독립적 단위, 즉 객체의 집합으로 프로그램을 표현하려는 프로그래밍 패러다임
- 상속 : 객체지향 프로그래밍의 핵심 개념으로, 어떤 객체의 프로퍼티 또는 메서드를 다른 객체가 상속받아 그대로 사용할 수 있는 것. 자바스크립트에서는 프로토타입을 기반으로 상속을 구현하여 불필요한 중복을 제거한다.
- prototype 프로퍼티 : 함수 객체만이 소유하는 prototype 프로퍼티는 생성자 함수가 생성할 인스턴스의 프로토타입을 가리킨다. 
- 오버라이딩 : 상위 클래스가 가지고 있는 메서드를 하위 클래스가 재정의하여 사용하는 방식이다.
- 오버로딩 : 함수 이름은 동일하지만 매개변수의 타입 또는 개수가 다른 메서드를 구현하고 매개변수에 의해 메서드를 구별하여 호출하는 방식이다.

<br>

### 객체
---
- 바인딩 : 식별자와 값을 연결하는 과정. 예를 들어, 변수 선언은 변수 이름(식별자)과 확보된 메모리 공간의 주소를 바인딩하는 것이다.
- 일급 객체 : 다음과 같은 조건을 만족하는 객체. 첫 번째, 무명의 리터럴로 생성할 수 있다. 즉, 런타임에 생성이 가능하다. 두 번째, 변수나 자료구조(객체, 배열등)에 저장할 수 있다. 세 번째, 함수의 매개변수에 전달할 수 있다. 네 번째, 함수의 반환값으로 사용할 수 있다.

<br>

### 클래스
---
- 프로토타입 메서드 : 인스턴스가 프로토타입 체이닝을 통해 마치 자신의 것처럼 호출할 수 있는 메서드
- 스태틱 메서드 : 생성자 함수(클래스) 자신만이 호출할 수 있는 메서드

### 실행컨텍스트
---
- 실행컨텍스트 : 실행 컨텍스트는 소스코드를 실행하는 데 필요한 환경을 제공하고 코드의 실행 결과를 실제로 관리하는 영역 // 구체적으로 실행 컨텍스트는 식별자(변수, 함수, 클래스등의 이름)를 등록하고 관리하는 스코프와 코드 실행 순서 관리를 구현한 내부 메커니즘으로, 모든 코드는 실행 컨텍스트를 통해 실행되고 관리된다. // 식별자와 스코프는 실행 컨텍스트의 렉시컬 환경으로 관리하고 코드 실행 순서는 실행 컨텍스트 스택으로 관리한다.
- 렉시컬 환경 : 식별자와 식별자에 바인딩된 값, 그리고 상위 스코프에 대한 참조를 기록하는 자료구조로 실행 컨텍스트를 구성하는 컴포넌트다.
- 환경 레코드 : 스코프에 포함된 식별자를 등록하고 등록된 식별자에 바인딩된 값을 관리하는 저장소다.
- 외부 렉시컬 환경에 대한 참조 : 외부 렉시컬 환경에 대한 참조는 상위 스코프를 가리킨다.
- 소스코드의 타입
  - 전역 코드 : 전역에 존재하는 소스코드를 말한다.
  - 함수 코드 : 함수 내부에 존재하는 소스코드를 말한다.
  - eval 코드 : 빌트인 전역 함수인 eval 함수에 인수로 전달되어 실행되는 소스코드를 말한다.
  - 모듈 코드 : 모듈 내부에 존재하는 소스코드를 말한다.

<br>

### 클로저
---
- 클로저 : 외부 함수보다 중첩 함수가 더 오래 유지되는 경우 중첩 함수는 이미 생명 주기가 종료한 외부 함수의 변수를 참조할 수 있다. 이러한 중첨 함수를 클로저라고 부른다. // 클로저는 상태가 의도치 않게 변경되지 않도록 안전하게 은닉하고 특정 함수에게만 상태 변경을 허용하여 상태를 안전하게 변경하고 유지하기 위해 사용한다.


### 이벤트
---
- 이벤트 드리븐 프로그래밍 : 프로그램의 흐름을 이벤트 중심으로 제어하는 프로그래밍 방식
- 이벤트 핸들러 : 이벤트가 발생했을 때 브라우저에 호출을 위임한 함수. 브라우저는 처리해야할 특정 사건이 발생하면 이를 감지하여 이벤트를 발생시킨다. 이때, 이벤트가 발생했을 때 호출될 함수를 이벤트 핸들러라고 한다.
- 이벤트 전파 : DOM 트리 상에서 존재하는 DOM 요소 노드에 발생한 이벤트는 DOM 트리를 통해 전파된다.
  - 캡처링 단계 : 이벤트가 상위 요소에서 하위 요소 방향으로 전파
  - 타겟 단계 : 이벤트가 이벤트 타겟에 도달
  - 버블링 단계 : 이벤트가 하위 요소에서 상위 요소로 전파

### 기타
---
- JSON : 클라이언트와 서버 간의 HTTP 통신을 위한 텍스트 데이터 포맷


출처 : 모던 자바스크립트 

