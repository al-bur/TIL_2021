# [210505] JavaScript - Ajax, axios

프론트엔드 개발자는 백엔드 개발자와 협업을 해서 웹 개발을 진행한다. 프론트엔드는 `클라이언트`단,  백엔드는 `서버`단에서 일어나는 작업들을 담당한다. 여기서 클라이언트와 서버를 이어주는 역할을 해주는 `통신` 역할이 필요한데 그 중 전체 웹페이지를 다시 렌더링 하지 않고 변화가 필요한 페이지의 일부만의 데이터를 로드하는, 비동기 통신을 가능하게 하는 `Ajax` 방법론에 대해서 살펴볼 예정이다.

<br>

### 1. AJax란?

---

 `Asynchronous Javascript And Xml`의 약자이며,  브라우저가 가지고 있는 `XMLHttpRequest` 객체를 이용해서 페이지의 일부만의 데이터를 비동기적으로 로드하는 구현 방식이라고 보면된다. 쉽게 말하면, AJax의 목적은 클라이언트가 화면 전환 없이 서버와의 정보를 교환하는 것이다.



**동기? 비동기?**

먼저, 동기와 비동기의 차이에 대해서 알아보면 좋을 것 같다.

- 동기 - 요청을 보낸 후 응답을 받아야지만 다음 동작이 이루어지는 방식이다. 순차적으로 일어나는 방식이기 때문에 앞의 동작이 끝나지 않으면 다음 동작은 일어나지 않는다. [`JavaScript`는 `single threaded`이기 때문에 동기적으로 동작한다.](https://stackoverflow.com/questions/2035645/when-is-javascript-synchronous)
- 비동기 -  요청을 보낸 후 응답과는 상관없이 다음방식이 동작하는 방식이다. 

<br>

### 2. Axios

---

위의 글을 통해 `Ajax`가 웹 상에서 클라이언트와 서버간의 비동기 통신을 가능케하는 방법론 인 것을 알았다. 

`Ajax`를 위한 `Axios`라는 라이브러리가 존재하는데, 많은 프론트엔드 개발자들이 `Ajax` 통신을 위해 `Axios`를 사용하고 있다. 

> https://github.com/axios/axios ->  해당 링크는 axois_github이므로 자세하게 내부 코드를 살펴보고 싶으면 방문해보셔도 좋을 것 같다.



Axios를 통해서 클라이언트에서 서버로 통신을 훨씬 편하게 보낼 수 있다.

```javascript
// Send a POST request
axios({
  method: 'post',
  url: '/user/12345',
  data: {
    firstName: 'Fred',
    lastName: 'Flintstone'
  }
});
```

위의 코드처럼 method, url, data등등 `JavaScript`의 객체를 형성해서 서버에 보내주게 되고 서버에서 `Response`를 받아옴으로써 비동기 통신이 가능하게 된다.

<br>
<br>

오늘은 간략하게, `ajax`와 `axios`를 알아보았고 추후 정보를 추가해보겠습니다~

