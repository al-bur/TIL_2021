# Kakao 지도 API를 React에서 사용해보기

많은 웹사이트에서 지도 기반 서비스를 제공할 때 카카오 지도 API를 사용하는 것을 많이 볼 수 있다. 
오늘은 해당 API를 React에서 사용해보는 것에 대한 글이다.

<br>

### 1. Kakao Delveloper에서 JavaScript API 키 발급 받기
---

- 먼저, API를 활용하기 위해서는 API 키를 발급받아야 한다.

- 아래 사이트에 접속한다.
developers.kakao.com/

- 로그인 후, 내 애플리케이션을 클릭한다.

- 내 애플리케이션 추가하기를 클릭하여 애플리케이션을 추가해준다.

![image](https://user-images.githubusercontent.com/64825713/132601959-5b205da6-46de-4328-a827-8a6e3745fdc3.png)

<br>

- "앱 설정 > 요약 정보"에 가면 JavaScript 키가 발급된 것을 볼 수 있다.

<br>

### 2. React 코드 작성
---

이제, API 키를 발급받았으니, React Project를 만들어 코드를 작성하여 지도를 띄워보자

<br>

- `index.html`에 아래의 코드를 넣어준다.

```
<script type="text/javascript" src="//dapi.kakao.com/v2/maps/sdk.js?appkey=발급받은 APP KEY를 넣으시면 됩니다."></script>
```

<br>

- 그리고 react 컴포넌트에 지도를 띄워주는 코드와 약간의 css를 작성해준다.
* 기존에는 javascript 코드로 작성되어 있는데, 이를 react 코드로 고치기 위해서 `useRef`를 활용하여 직접 DOM을 조작해주었다.


```javascript
import "./App.css";
import { useEffect, useRef } from "react";
import styled from "styled-components";

const Wrapper = styled.div`
  height: 100vh;
`;

const MapTitle = styled.h1`
  position: fixed;
  top: 5%;
  left: 3%;
  z-index: 123;
`;

const MapContainer = styled.div`
  width: 100%;
  height: 100%;
`;

function App() {
  const kakaoMap = useRef(null);
  // 지도에 대한 옵션
  const options = {
    //지도의 중심좌표
    center: new window.kakao.maps.LatLng(33.450701, 126.570667),
    level: 3, //지도의 레벨
  };
  useEffect(() => {
    // 지도를 출력해준다.
    new window.kakao.maps.Map(kakaoMap.current, options);
  }, []);

  return (
    <Wrapper>
      <MapTitle>this is map</MapTitle>
      <MapContainer ref={kakaoMap}></MapContainer>
    </Wrapper>
  );
}

export default App;

```

<br>

### 3. 결과물 
---

![image](https://user-images.githubusercontent.com/64825713/132602686-096ca0ce-1ca8-4a2a-92e4-0dcb558e173c.png)


