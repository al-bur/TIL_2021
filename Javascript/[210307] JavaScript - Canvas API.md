# [210307] [JavaScript - Canvas API](https://developer.mozilla.org/ko/docs/Web/API/Canvas_API)

### 1. 주제를 선택한 이유

---

`그림판 만들기` 작업을 진행중인데 `canvas API`에 관한 지식이 필요하여 공부 후 정리합니다.

<br>

### 2.  What is Canvas API
---


>The **Canvas API** provides a means for drawing graphics via [JavaScript](https://developer.mozilla.org/en-US/docs/Web/JavaScript) and the [HTML](https://developer.mozilla.org/en-US/docs/Web/HTML) [``](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/canvas) element. Among other things, it can be used for animation, game graphics, data visualization, photo manipulation, and real-time video processing.

`Canvas API`는 JavaScript와 HTML을 통해서 그래픽을 그리기 위한 도구들을 제공한다. 많은 기능들 중에서, 애니메이션, 게임 그래픽, 데이터 가시화, 사진 수정과 실시간 비디오 처리에 사용된다.

<br>

> The Canvas API largely focuses on 2D graphics. The [WebGL API](https://developer.mozilla.org/en-US/docs/Web/API/WebGL_API), which also uses the `<canvas>` element, draws hardware-accelerated 2D and 3D graphics.

`Canvas API`는 주로 2D 그래픽에 초점을 맞추고 있다. `WebGL API`도 `<canvas>`를 작성하여 사용될 수 있는데, 이는 2D와 3D 그래픽을 그려낸다.

<br>

```HTML
<canvas id="canvas"><</canvas>
```

HTML에서 위의 방식으로 사용할 수 있다.

<br>

### 3. How to use (JavaScript)

---

>The [`Document.getElementById()`](https://developer.mozilla.org/en-US/docs/Web/API/Document/getElementById) method gets a reference to the HTML `<canvas>` element. Next, the [`HTMLCanvasElement.getContext()`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLCanvasElement/getContext) method gets that element's context—the thing onto which the drawing will be rendered.

`Document.getElementById()` 메서드를 통해 HTML에 있는 `<canvas>`요소에 접근한다. 그 다음, `HTMLCanvasElement.getContext()` 메서드를 통해 그 요소의 `context`에 접근을 해서 그리기를 진행한다.

<br>
<br>

```javascript
const canvas = document.getElementById('canvas');
const ctx = canvas.getContext('2d');

ctx.fillStyle = 'green';
ctx.fillRect(10, 10, 150, 100);
```

>The actual drawing is done using the [`CanvasRenderingContext2D`](https://developer.mozilla.org/en-US/docs/Web/API/CanvasRenderingContext2D) interface. The [`fillStyle`](https://developer.mozilla.org/en-US/docs/Web/API/CanvasRenderingContext2D/fillStyle) property makes the rectangle green. The [`fillRect()`](https://developer.mozilla.org/en-US/docs/Web/API/CanvasRenderingContext2D/fillRect) method places its top-left corner at (10, 10), and gives it a size of 150 units wide by 100 tall.

`CanvasRenderingContext2D` 인터페이스를 사용해서 실제 그리기 작업이 진행된다. `fillStyle` 프로퍼티가 초록색 사각형을 만든다. `fillRect()` 메서드가 (10, 10)에 위치하게 하고 가로 150 x 세로 100 크기를 가지게 한다.

<br>

![image](https://user-images.githubusercontent.com/64825713/110235088-87203900-7f71-11eb-8b51-bd8db131413c.png)

<br>

### 4. Libraries

---

>The Canvas API is extremely powerful, but not always simple to use. The libraries listed below can make the creation of canvas-based projects faster and easier.

`CanvasAPI`는 강력하지만 사용하기 간단하지 않다. 아래에 나열된  `libraries`는 캔버스 기반의 프로젝트를 더 빠르고 쉽게 진행하는 데 도움을 준다.

<br>

> - [EaselJS](http://www.createjs.com/easeljs) is an open-source canvas library that makes creating games, generative art, and other highly graphical experiences easy.
> - [Fabric.js](http://fabricjs.com/) is an open-source canvas library with SVG parsing capabilities.
> - [heatmap.js](https://www.patrick-wied.at/static/heatmapjs/) is an open-source library for creating canvas-based data heat maps.
> - [JavaScript InfoVis Toolkit](http://thejit.org/) creates interactive data visualizations.

- `EaseIJS`는 오픈소스 canvas library로서 게임, generative art, 그리고 다른 고-그래픽 작업들을 쉽게 할 수 있게 도와준다.
- `Fabric.js`는 `SVG parsing capabilites`를 제공하는 오픈소스 canvas library다.
- `heatmap.js`는 heatmap을 제작할 수 있는 오픈소스 library다.
- `JavaScript InfoVis Toolkit`을 통해서는 상호작용하는 데이터 시각화 작업들이 가능하다.

<br>

### 5. Browser compatibility

---

![image](https://user-images.githubusercontent.com/64825713/110235080-7bcd0d80-7f71-11eb-83f5-355a72f44a93.png)

from https://caniuse.com/?search=canvas
