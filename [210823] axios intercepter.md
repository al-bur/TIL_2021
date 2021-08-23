# axios intercerptor

#### 프로젝트에서 적용한 axios interceptor에 관한 글을 작성해보았습니다.

<br>

현재, homedong 웹사이트의 로직은 이렇습니다. 

사용자 로그인 -> 로그인 성공 후 메인페이지 이동 -> 회원 정보 불러오는 api 요청 -> 회원 정보 state에 저장

<br>

정상적으로 작동이 되면, 메인페이지로 이동됨과 동시에 회원정보까지 redux state에 저장이 되어여 합니다.

<br>

하지만, 문제가 발생했습니다😥

<br>

회원정보를 불러오는 api 요청시 사용자의 JWT 토큰이 request header에 담겨야 합니다.

하지만, header에 담기지 않고 페이지 새로고침을 해줘야만 api header에 토큰이 담기는 로직이 실행되는 것을 확인할 수 있었습니다.

<br>

맞습니다..😯


문제는 axios header에 토큰을 담아주는 로직이 있는 http-common.js 파일이 화면이 전체 렌더링 될때만 실행된다는 것이었습니다.



이를 해결하려면, axios에 변화를 주는 것을 찾아야 했습니다. 수많은 구글링 끝에 axios 요청을 보내기 전에 axios를 customize할 수 있는 방법을 찾아냈습니다. 

<br>

axios-interceptor를 통해서입니다.
말그대로 axios 요청을 보내 기전과 후에 axios를 customize 할 수 있습니다.

<br>

아래는 코드입니다.


```
import baseAxios from 'axios';
import { getToken } from './JWT-common';

const axios = baseAxios.create({
  baseURL: '/',
  headers: {
    'Content-Type': 'application/json',
  },
});

// 인터셉트
axios.interceptors.request.use((config) => {
  config.headers.Authorization = `Bearer ${getToken()}`;
  return config;
});

export default axios;
```


해당 방법을 통해서, axios 요청을 보내기 전에 header에 토큰을 담아줄 수 있었습니다!
