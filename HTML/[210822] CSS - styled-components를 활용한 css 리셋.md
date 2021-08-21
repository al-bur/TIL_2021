# [210822] CSS - styled-components를 활용한 css 리셋



### 1. reset을 해주는 이유
---

- 사용자들은 특정 브라우저만 사용하는 것이 아니고 다양한 브라우저를 사용합니다.

- 각 브라우저에서 제공하는 스타일들은 표준화 되어 있지 않아 각 브라우저마다 출력해주는 모양이 다를 수 있습니다.

- 개발 단계에서 의도했던 대로 모든 사용자의 화면에서 동일하게 출력해주기 위해 초기화(reset)을 해야합니다.

<br>

### 2. styled-components를 활용한 css 리셋
---

react에서 style을 적용하기위해 자주 사용되는 styled-components를 활용하여 css리셋을 해보겠습니다.

<br>

### 2-1 GlobalStyles.js 생성 후 reset 코드 작성

```javascript
import reset from 'styled-reset';
import { createGlobalStyle } from 'styled-components';

const globalStyles = createGlobalStyle`
    ${reset}
    *{
      margin: 0;
      padding: 0;
      list-style: none;
      text-decoration: none;
      box-sizing: border-box;
    }
    body, html {
      margin: 0;
      padding: 0;
      font-size: 16px;
    }
    button {
      background: none;
      color: inherit;
      border: none;
      cursor: pointer;
      outline: inherit;
    }
    
    a {
      color: inherit;
      text-decoration: none;
    }
    
    li {
      list-style: none;
    }
    
    input:focus {
      outline: none;
    }
`;

export default globalStyles;
```

<br>

### 2-2 해당 파일을 App.js(root)에 import 후 적용

```javascript
import React from 'react';
import { BrowserRouter, Route } from 'react-router-dom';
import styled from 'styled-components';
import Home from './features/home/Home';
import GlobalStyles from './GlobalStyles';

const Wrapper = styled.div`
  background-color: rgba(246, 245, 253, 1);
`;

function App() {
  return (
      <Wrapper>
        <GlobalStyles />
        <BrowserRouter>
          <Route path="/" exact component={Home} />
        </BrowserRouter>
      </Wrapper>
    </StylesProvider>
  );
}

export default App;
```


이렇게 해주면 css 리셋이 됩니다😀
