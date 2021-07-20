# [210720] web_framework - React Hooks(useState)

React에서 Hook은 class를 작성하지 않고도 state와 다른 React의 기능들을 사용할 수 있게 해준다. 기존에 class 형식의 component를 사용해야 state를 내부적으로 관리하고 사용할 수 있던 것에서 Hook을 사용하면 function component에서도 state를 사용할 수 있게 되었다. 오늘은 Hook에서 많이 사용되는 `useState`를 사용하여 작성해본 `custom Hook`을 소개하려고 한다.

<br>

### 1. 기본적인 useState

---

```javascript
import React, { useState } from "react";
import "./styles.css";

export default function App() {
  // (1)이라는 초기 값을 item에 입력
  const [item, setItem] = useState(1);
  const incrementItem = () => setItem(item + 1);
  const decrementItem = () => setItem(item - 1);
  return (
    <div>
      <h1> helllo </h1>
      <button onClick={incrementItem}> + </button>
      {item}
      <button onClick={decrementItem}> - </button>
    </div>
  );
}

const rootElement = document.getElementById("root");
ReactDOM.render(
    <App />
  rootElement
);
```


<br>


### 2. useInput

---

```javascript
const useInput = (initialValue) => {
  const [value, setValue] = useState(initialValue);
  const onChange = (event) => {
    console.log(event.target.value);
  };
  // value랑 함수를 return 해서 App 함수에서 사용할 수 있음!!!😀
  return { value, onChange };
};

const App = () => {
  const name = useInput("Mr.");
  return (
    <div>
      <h1> helllo </h1>
      <input type="text" placeholder="name" {...name} />
    </div>
  );
};

const rootElement = document.getElementById("root");
ReactDOM.render(
    <App />,
  rootElement
);
```


<br>


### 3. useInput + validator

---

```javascript
import React, { useState, StrictMode } from "react";
import ReactDOM from "react-dom";

const useInput = (initialValue, validator) => {
  const [value, setValue] = useState(initialValue);
  const onChange = (event) => {
    const {
      target: { value }
    } = event;
    let willUpdate = true;
    if (typeof validator === "function") {
      willUpdate = validator(value);
    }
    if (willUpdate) {
      setValue(value);
    }
  };
  return { value, onChange };
};

const App = () => {
	// true, false로 반환되는 함수 설정
  const maxLen = (value) => value.length <= 10;
  const name = useInput("Mr.", maxLen);
  return (
    <div>
      <h1> helllo </h1>
      <input type="text" placeholder="name" {...name} />
    </div>
  );
};

const rootElement = document.getElementById("root");
ReactDOM.render(
    <App />,
  rootElement
);
```



<br>

### 4. useTabs

---

```javascript
import React, { useState, StrictMode } from "react";
import ReactDOM from "react-dom";
import "./styles.css";

const content = [
  {
    tab: "Section 1",
    content: "this is the content of section 1"
  },
  {
    tab: "Section 2",
    content: "this is the content of section 2"
  }
];

const useTabs = (initialValue, allTabs) => {
  const [currentIdx, setIdx] = useState(initialValue);
  return {
    currentItem: allTabs[currentIdx],
    // setIdx를 통해 re-render가 된다는 것을 명심!!
    changeItem: setIdx
  };
};

const App = () => {
  const { currentItem, changeItem } = useTabs(0, content);
  return (
    <div className="App">
      {content.map((section, index) => (
        <button key={index} onClick={() => changeItem(index)}>
          {section.tab}
        </button>
      ))}
      <div>{currentItem.content}</div>
    </div>
  );
};

const rootElement = document.getElementById("root");
ReactDOM.render(
  <StrictMode>
    <App />
  </StrictMode>,
  rootElement
);
```

