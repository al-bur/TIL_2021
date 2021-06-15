# [210213] What is HTTP?(2)

### 1. 주제를 선택한 이유

---

저번에,  `frontend-roadmap`에서 `Internet` 관련해서 인터넷이 어떻게 작동되는지?에 대해서 공부를 했었다.

그래서 이번에는 `What is HTTP?`에 대해서 조사해보고 정리해보려고한다. 어제에 이어 진행하겠습니다

사이트는 `Mozilla`를 참고하였습니다.

<br>

### 2. [HTTP](https://developer.mozilla.org/en-US/docs/Web/HTTP/Overview)

#### 2.1 [Basic aspects of HTTP](https://developer.mozilla.org/en-US/docs/Web/HTTP/Overview#basic_aspects_of_http)

---

> **HTTP is simple**
>
> HTTP is generally designed to be simple and human readable, even with the added complexity introduced in HTTP/2 by encapsulating HTTP messages into frames. HTTP messages can be read and understood by humans, providing easier testing for developers, and reduced complexity for newcomers.

**HTTP는 간단하다**

`HTTP`는 HTTP 메세지들을 프레임으로 캡슐화하는 복잡한 과정이 더해져도  대체적으로 간단하고 사람이 읽을 수 있게 디자인 되었다.  `HTTP` 메세지들은 가독성 있고 사람들이 이해할 수 있다. 그렇다 보니 개발자들에게 더 쉬운 테스팅을 제공하고 새로운 입문자들은 덜 복잡하게 접근 할 수 있다.

<br>

> **HTTP is extensible**
>
> Introduced in HTTP/1.0, [HTTP headers](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers) make this protocol easy to extend and experiment with. New functionality can even be introduced by a simple agreement between a client and a server about a new header's semantics.

**HTTP는 확장성이 있다.**

`HTTP 1.0`에서 소개되었듯이, `HTTP headers`는 이 프로토콜이 확장과 실험을 쉽게 할 수 있게 해주었다. 새로운 동작/기능도 클라이언트와 서버사이의 새로운 header's semantics에 대한 간단한 agreement를 통해서 도입이 가능하다.

<br>

> **HTTP is stateless, but not sessionless**
>
> HTTP is stateless: there is no link between two requests being successively carried out on the same connection. This immediately has the prospect of being problematic for users attempting to interact with certain pages coherently, for example, using e-commerce shopping baskets. But while the core of HTTP itself is stateless, HTTP cookies allow the use of stateful sessions. Using header extensibility, HTTP Cookies are added to the workflow, allowing session creation on each HTTP request to share the same context, or the same state.

**HTTP는 무상태지만 sessionless이다 **

`HTTP`는 무상태이다; 같은 연결상에 연속적으로 실행되는 두 개의 `requests` 사이에 링크가 없다. 이것은 특정한 페이지들과 일관되게 상호작용하려고 시도하는 사용자들에게 문제가 있을 수도 있다는 전망을 가져다 준다. 이커머스 쇼핑 장바구니를 이용하는 것이 한 예이다.



<br>



#### 2.2 [What can be controlled by HTTP](https://developer.mozilla.org/en-US/docs/Web/HTTP/Overview#what_can_be_controlled_by_http)

---

>This extensible nature of HTTP has, over time, allowed for more control and functionality of the Web. Cache or authentication methods were functions handled early in HTTP history. The ability to relax the *origin constraint*, by contrast, has only been added in the 2010s.\
>
>Here is a list of common features controllable with HTTP.
>
>- *[Caching](https://developer.mozilla.org/en-US/docs/Web/HTTP/Caching)*
>  How documents are cached can be controlled by HTTP. The server can instruct proxies and clients, about what to cache and for how long. The client can instruct intermediate cache proxies to ignore the stored document.
>- *Relaxing the origin constraint*
>  To prevent snooping and other privacy invasions, Web browsers enforce strict separation between Web sites. Only pages from the **same origin** can access all the information of a Web page. Though such constraint is a burden to the server, HTTP headers can relax this strict separation on the server side, allowing a document to become a patchwork of information sourced from different domains; there could even be security-related reasons to do so.
>- *Authentication*
>  Some pages may be protected so that only specific users can access them. Basic authentication may be provided by HTTP, either using the [`WWW-Authenticate`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/WWW-Authenticate) and similar headers, or by setting a specific session using [HTTP cookies](https://developer.mozilla.org/en-US/docs/Web/HTTP/Cookies).
>- *[Proxy and tunneling](https://developer.mozilla.org/en-US/docs/Web/HTTP/Proxy_servers_and_tunneling)*
>  Servers or clients are often located on intranets and hide their true IP address from other computers. HTTP requests then go through proxies to cross this network barrier. Not all proxies are HTTP proxies. The SOCKS protocol, for example, operates at a lower level. Other protocols, like ftp, can be handled by these proxies.
>- *Sessions*
>  Using HTTP cookies allows you to link requests with the state of the server. This creates sessions, despite basic HTTP being a state-less protocol. This is useful not only for e-commerce shopping baskets, but also for any site allowing user configuration of the output.



<br>



#### 2.3 [HTTP flow](https://developer.mozilla.org/en-US/docs/Web/HTTP/Overview#http_flow)

---

>When a client wants to communicate with a server, either the final server or an intermediate proxy, it performs the following steps:
>
>1. Open a TCP connection: The TCP connection is used to send a request, or several, and receive an answer. The client may open a new connection, reuse an existing connection, or open several TCP connections to the servers.
>2. Send an HTTP message: HTTP messages (before HTTP/2) are human-readable. With HTTP/2, these simple messages are encapsulated in frames, making them impossible to read directly, but the principle remains the same. For example:
>3. If HTTP pipelining is activated, several requests can be sent without waiting for the first response to be fully received. HTTP pipelining has proven difficult to implement in existing networks, where old pieces of software coexist with modern versions. HTTP pipelining has been superseded in HTTP/2 with more robust multiplexing requests within a frame.

<br>

#### 3. 비고

---

- 추가적으로, 내일 더 공부하겠습니다.
