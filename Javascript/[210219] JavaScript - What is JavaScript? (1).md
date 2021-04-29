# [210219] What is JavaScript? (1)

### 1. 주제를 선택한 이유

---

`front-end 개발자`에게는 `javascript`는 기본이다.  그래서 오늘은  `javascript`가 기본적으로 무엇일까?에 대해서 공부해보았다.

MDN WEB Docs를 참고하였다.

<br>

## 2. [Javascript](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/First_steps/What_is_JavaScript)

### 2.1 A high-level definition

---

>JavaScript is a scripting or programming language that allows you to implement complex features on web pages — every time a web page does more than just sit there and display static information for you to look at — displaying timely content updates, interactive maps, animated 2D/3D graphics, scrolling video jukeboxes, etc. — you can bet that JavaScript is probably involved. It is the third layer of the layer cake of standard web technologies, two of which ([HTML](https://developer.mozilla.org/en-US/docs/Learn/HTML) and [CSS](https://developer.mozilla.org/en-US/docs/Learn/CSS)) we have covered in much more detail in other parts of the Learning Area. we can add some JavaScript to implement dynamic behavior

`JavaScript`는 웹페이지상에 복잡한 features들을  사용할 수 있게 해주는 스크립팅 또는 프로그래밍 언어이다 --- 주기적으로 업데이트 되는 컨텐츠를 보여주거나, 상호작용하는 지도, 2D/3D  애니메이션 그래픽, 비디오 주크박스 등등에는 자바스크립트가 이용이 되었을 것이라고 확신한다.--`HTML`과 `CSS`에 이은 웹 기술들의 세 번째 layer이다. `JavaScript`를 이용하면 역동적인 동작들을 추가할 수 있다.

<br>

### 2.1 What can it really do?

---

>The core client-side JavaScript language consists of some common programming features that allow you to do things like:
>
>- Store useful values inside variables. In the above example for instance, we ask for a new name to be entered then store that name in a variable called `name`.
>- Operations on pieces of text (known as "strings" in programming). In the above example we take the string "Player 1: " and join it to the `name` variable to create the complete text label, e.g. ''Player 1: Chris".
>- Running code in response to certain events occurring on a web page. We used a `click` event in our example above to detect when the button is clicked and then run the code that updates the text label.
>- And much more!

 핵심 클라이언트-사이드인 `JavaScript` 아래 사항들을 가능하게 해주는 몇 가지의 프로그래밍 features들로 구성되어 있다:

- 변수에 유용한 values들을 저장한다. 예를 들어,  기입할 새로운 이름을 요구해서 그 정보를  `name`이라는 변수에 저장한다.
- 텍스트 조각들에 대한 동작들이 가능하다. 예를 들어, `Player 1:`를  `name` 변수와 합쳐줘서 `Player 1: Chris`로 만들어 줄 수 있다.
- 웹페이에서 발생하는 특정한 사건들에 반응해서 코드를 작동시킨다. `click` 이벤트를 사용해서 버튼이 클릭 되는 지 감지할 수 있고 텍스트 라벨을 업데이트하는 코드를 실행시킬 수 있다.
- 그리고 더 많은 것들을 할 수 있다!!!

<br>

> What is even more exciting however is the functionality built on top of the client-side JavaScript language. So-called **Application Programming Interfaces** (**APIs**) provide you with extra superpowers to use in your JavaScript code.
>
> APIs are ready-made sets of code building blocks that allow a developer to implement programs that would otherwise be hard or impossible to implement. They do the same thing for programming that ready-made furniture kits do for home building — it is much easier to take ready-cut panels and screw them together to make a bookshelf than it is to work out the design yourself, go and find the correct wood, cut all the panels to the right size and shape, find the correct-sized screws, and *then* put them together to make a bookshelf.

더욱 흥미로운 것은 클라이언트-사이드 `JavaScript` 언어가 갖춘 기능성이다. `Application Programming Interfaces (APIs)`는 `Javascript` 코드에서  사용할 수 있는 슈퍼파워를 제공한다!!!...

API는 개발자들에게 구현하기 어렵거나 구현하기 불가능한 프로그램들을 사용하게 만들어주는 이미 만들어진 코드들을 제공해준다. ready-made 가구 키트 같은 역할을 한다.

<br>

대표적인 APIs는 아래 두 가지가 있을 수 있다.

<br>

> **Browser APIs** are built into your web browser, and are able to expose data from the surrounding computer environment, or do useful complex things. For example:
>
> - The [`DOM (Document Object Model) API`](https://developer.mozilla.org/en-US/docs/Web/API/Document_Object_Model) allows you to manipulate HTML and CSS, creating, removing and changing HTML, dynamically applying new styles to your page, etc. Every time you see a popup window appear on a page, or some new content displayed (as we saw above in our simple demo) for example, that's the DOM in action.
> - The [`Geolocation API`](https://developer.mozilla.org/en-US/docs/Web/API/Geolocation) retrieves geographical information. This is how [Google Maps](https://www.google.com/maps) is able to find your location and plot it on a map.
> - The [`Canvas`](https://developer.mozilla.org/en-US/docs/Web/API/Canvas_API) and [`WebGL`](https://developer.mozilla.org/en-US/docs/Web/API/WebGL_API) APIs allow you to create animated 2D and 3D graphics. People are doing some amazing things using these web technologies —see [Chrome Experiments](https://www.chromeexperiments.com/webgl) and [webglsamples](http://webglsamples.org/).
> - [Audio and Video APIs](https://developer.mozilla.org/en-US/docs/Web/Guide/Audio_and_video_delivery) like [`HTMLMediaElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLMediaElement) and [`WebRTC`](https://developer.mozilla.org/en-US/docs/Web/API/WebRTC_API) allow you to do really interesting things with multimedia, such as play audio and video right in a web page, or grab video from your web camera and display it on someone else's computer (try our simple [Snapshot demo](https://chrisdavidmills.github.io/snapshot/) to get the idea).

`Browser APIs`는 웹브라우저안에 내장되고 둘러쌓여있는 컴퓨터 환경에서부터 데이터를 드러낼 수 있다. 또는, 아래의 예들 같은 유용한 것들을 할 수 있게 해준다. 

- `DOM(Document Object Model) API`는 HTML, CSS를 조작할 수 있게 해주고, HTML을 생성, 제거, 변경하는 것, 그리고 페이지에 역동적으로 새로운 스타일들을 적용시키게 해준다. 페이지에서 나타는 팝업윈도우, 새로운 컨텐츠가 보여지는 것 모두, DOM이 작동되는 것이다.
- `Geolocation API`는 지리학적인 정보를 가지고 있다. 이는 어떻게 Google Maps가 지도에서 위치를 찾을 수 있는지를 설명해준다.
- `Canvas`와 `WebGL` `APIs`는 2D와 3D 그래픽을 만드는 데 도움을 준다. 사람들을 이 웹기술들을 이용해서 몇몇의 어메이징한 일들을 해내고 있다. 
- `Audio and Video APIs`는 오디오나 비디오를 웹페이지에서 바로 재생하거나 웹카메라에서 비디오 정보를 받아서 다른 사람의 컴퓨터에서 보여주는 것과 같이, 멀티미디어를 가지고 흥미로운 것들을 하게 해준다.



<br>

>**Third party APIs** are not built into the browser by default, and you generally have to grab their code and information from somewhere on the Web. For example:
>
>- The [Twitter API](https://dev.twitter.com/overview/documentation) allows you to do things like displaying your latest tweets on your website.
>- The [Google Maps API](https://developers.google.com/maps/) and [OpenStreetMap API](https://wiki.openstreetmap.org/wiki/API) allows you to embed custom maps into your website, and other such functionality.



<br>

