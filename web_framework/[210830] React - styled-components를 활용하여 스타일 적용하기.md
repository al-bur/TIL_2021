
# [210830] React - styled-components를 활용하여 스타일 적용하기

### React에서 컴포넌트를 스타일링해주는 방법은 여러 가지가 있습니다.

<br>

1. css파일을 생성해서 import해서 className으로 적용한 스타일링 방식

2. 1번의 방법으로는 global로 css가 적용이 되므로, module 방식을 이용한 스타일링 방식

3. styled-components를 이용한 스타일링

4. React UI Framework인 element-UI를 기본적으로 활용하고, 제공되는 컴포넌트를 makeStyles()를 활용하여 커스터마이징 해주는 스타일링 방식

<br>

### styled-components를 활용하여 React 컴포넌트를 스타일링해주기
---

<br>

1. 기본적인 설치
```
npm install styled-components
```

<br>

2. import

```
import styled from 'styled-components';
```

<br>

3. 스타일링
styled-components는 JS 파일에서 css를 작성할 수 있게 해주는 도구라고 보면 됩니다. 이 때문에, 모든 css 기능들을 사용할 수 있습니다.

> As you can see, styled-components lets you write actual CSS in your JavaScript. This means you can use all the features of CSS you use and love, including (but by far not limited to) media queries, all pseudo-selectors, nesting, etc. (styled-component 공식 홈페이지 본문 中)

<br>

아래는 styled-components를 사용해서 Wrapper와 LoginContainer라는 customized 된 div들입니다.

```
const Wrapper = styled.div`
  height: 100%;
  display: flex;
  justify-content: center;
  align-items: center;
`;

const LoginContainer = styled.div`
  height: 80%;
  width: 80%;
  background-color: white;
  display: flex;
  justify-content: center;
  flex-direction: column;
  align-items: center;
`;
```

4. render
customized된 Wrapper와 LoginContainer를 사용해주면 됩니다.

```
return (
    <Wrapper>	
       <LoginContainer>
       </LoginContainer>
    </Wrapper>
)
```

출처
https://styled-components.com/﻿
