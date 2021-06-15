# [210211] What is HTTP?(1)

### 1. 주제를 선택한 이유

---

저번에,  `frontend-roadmap`에서 `Internet` 관련해서 인터넷이 어떻게 작동되는지?에 대해서 공부를 했었다.

그래서 이번에는 `What is HTTP?`에 대해서 조사해보고 정리해보려고한다.

사이트는 `Mozilla`를 참고하였습니다.

<br>

### 2. [HTTP](https://developer.mozilla.org/en-US/docs/Web/HTTP/Overview)

#### 2.1 definition of HTTP

---

> **HTTP** is a [protocol](https://developer.mozilla.org/en-US/docs/Glossary/Protocol) which allows the fetching of resources, such as HTML documents. It is the foundation of any data exchange on the Web and it is a client-server protocol, which means requests are initiated by the recipient, usually the Web browser. A complete document is reconstructed from the different sub-documents fetched, for instance text, layout description, images, videos, scripts, and more.

HTML 문서들 같이 여러 리소스들을 가져오는 것을 허락해주는 하나의 프로토콜이다. HTTP는 웹 상에서 발생하는 데이터 교환의 기반이고 클라이언트-서버 프로토콜이다; 요청들은 웹 브라우저같이 `recipient`에 의해 시작되는 것을 의미한다. 하나의 완전한 문서는 텍스트, 레이아웃에 대한 설명, 이미지, 비디어, 스크립드등 같은 다른 하위 문서들을 가져와서 재구축 되어진다.

<br>

![image](https://user-images.githubusercontent.com/64825713/107652724-385de700-6cc4-11eb-8a3e-a7a74bfd3a42.png)

> Clients and servers communicate by exchanging individual messages (as opposed to a stream of data). The messages sent by the client, usually a Web browser, are called *requests* and the messages sent by the server as an answer are called *responses*.

클라이언트와 서버는 개인적인 메세지(데이터의 흐름과 반대됨)들을 교환하는 방식으로 의사소통을 한다. 클라이언트(대게, 웹 브라우저)에 의해서 보내진 메세지들은 `requests`라고 불리며 서버에의해서 보내진 메세지들은 `responses`라고 불린다. 

<br>

![image](https://user-images.githubusercontent.com/64825713/107652787-4ad82080-6cc4-11eb-9251-6a7d98099d7d.png)

>Designed in the early 1990s, HTTP is an extensible protocol which has evolved over time. It is an application layer protocol that is sent over [TCP](https://developer.mozilla.org/en-US/docs/Glossary/TCP), or over a [TLS](https://developer.mozilla.org/en-US/docs/Glossary/TLS)-encrypted TCP connection, though any reliable transport protocol could theoretically be used. Due to its extensibility, it is used to not only fetch hypertext documents, but also images and videos or to post content to servers, like with HTML form results. HTTP can also be used to fetch parts of documents to update Web pages on demand.

1990대 초에 디자인된, `HTTP`는 계속 발전을 되어온 확장성이 있는 프로토콜이다. `HTTP`는 다른 신뢰operationㅇ성있는 transport protocol도 이론 적으로는 사용 가능하지만 TCP 또는 TLS-encrypted TCP 커넥션을 통해서 전달되는 `application layer protocol`이다. `HTTP`의 확장성 덕분에, hypertext documents 뿐만 아니라 이미지와 비디오를 가져오는 데 사용될 뿐만 아니라 HTML form으로 서버에 컨텐츠를 보내는 데도 사용된다. `HTTP`는 웹페이지 업데이트에 대한 수요가 있을 때 문서의 일부를 가져오는 데도 사용된다. 

<br>

#### 2.2 Components of HTTP-based systems

---

>HTTP is a client-server protocol: requests are sent by one entity, the user-agent (or a proxy on behalf of it). Most of the time the user-agent is a Web browser, but it can be anything, for example a robot that crawls the Web to populate and maintain a search engine index.

`HTTP`는 클라이언트-서버 프로토콜이다: `requests`는 하나의 개체인, user-agent에 의해서 보내진다. (아니면 `proxy`가 사용될 수도 있음) 대부분의 경우에는, user-agent는 웹브라우저이지만 user-agent는 아무나 될 수 있다; 예를 들면, 검색 엔진 index를 채우고 유지하기 위해 웹을 크롤링하는 로봇도 user-agent가 될 수 있다.

<br>

> Each individual request is sent to a server, which handles it and provides an answer, called the *response*. Between the client and the server there are numerous entities, collectively called [proxies](https://developer.mozilla.org/en-US/docs/Glossary/Proxy_server), which perform different operations and act as gateways or [caches](https://developer.mozilla.org/en-US/docs/Glossary/Cache), for example.

각각의 `request`는 서버로 보내지고, 서버가 `request`를 다루고 그것에 대한 대답인 `response`를 제공한다. 클라이언트와 서버사이에는 수많은 개체들이 존재하는 데 이는 전체적으로 `proxies`라고 불린다. 이들은 여러 작업들을 실행하고 gateways나 caches로써 역할한다. 

예를 들면, 

![image](https://user-images.githubusercontent.com/64825713/107652814-54618880-6cc4-11eb-804a-1d53aab2cc88.png)

<br>

> In reality, there are more computers between a browser and the server handling the request: there are routers, modems, and more. Thanks to the layered design of the Web, these are hidden in the network and transport layers. HTTP is on top, at the application layer. Although important to diagnose network problems, the underlying layers are mostly irrelevant to the description of HTTP.

실제로는, 브라우저와 서버 사이에 `request`를 다루는 더 많은 컴퓨터가 존재한다 :  라우터, 모뎀등등이 있다. 레이어드 디자인을 갖춘 웹 덕분에, 이것들은 네트워크와 전송 계층들에 숨겨져있다. `HTTP`가 `application layer`에서 맨 꼭대기에 위치하고 있다. 네트워크 문제들을 진단하는 데 중요하지만, 밑에 위치한 계층들은 `HTTP`의 묘사와는 대부분 관계가 없다.

<br>

##### 2.2.1 Client: the user-agent

> The *user-agent* is any tool that acts on the behalf of the user. This role is primarily performed by the Web browser; other possibilities are programs used by engineers and Web developers to debug their applications.

`user-agent`는 사용자 대신하여 작동하는 도구다. 이 역할은 주로 웹 브라우저가 맡고 있다; 웹개발자와 엔지니어가 자신들의 응용프로그램을 디버깅하기위해 사용하는 프로그램일 수도 있다. 



> The browser is **always** the entity initiating the request. It is never the server (though some mechanisms have been added over the years to simulate server-initiated messages).
>
> To present a Web page, the browser sends an original request to fetch the HTML document that represents the page. It then parses this file, making additional requests corresponding to execution scripts, layout information (CSS) to display, and sub-resources contained within the page (usually images and videos). The Web browser then mixes these resources to present to the user a complete document, the Web page. Scripts executed by the browser can fetch more resources in later phases and the browser updates the Web page accordingly.



브라우저는 **항상** `request`를 시작하는 개체이다. 서버는 절대 아니다.

웹페이지를 표시하기 위해, 브라우저가 페이지를 표시해주는 HTML 요소들을 가져오기 위해서 오리지널 request를 보낸다. 



#### 3. 비고

---

- 추가적으로, 내일 더 공부하겠습니다.
