# [210509] CS - CSR vs SSR

### 1. CSR(Client-Side-Rendering)

---

클라이언트 사이드에서 `JavaScript`가 동작하면서 브라우저에서 페이지를 직접 렌더링 하는 것

점점 더 복잡해지는 웹페이지를 구현하기 위해서 전통적인 방식의 SSR보다는 CSR로 웹을 구현하는 경우가 많아짐

<br>

![CSR-process](https://user-images.githubusercontent.com/64825713/117573045-d79e4900-b110-11eb-8ef3-7e97f75deda6.png)

<br>

**장점**

- 사용자의 행동에 따라 필요한 부분만 다시 읽어들이기때문에 SSR 보다 조금 더 빠른 인터랙션 가능
- page 전체를 요청하지 않고 페이지에 필요한 부분만 변경하게 하기 때문에, 모바일 네트워크에서도 빠른 속도로 렌더링이 가능
- lazy loading을 지원해줌
  
  

<br>

**단점**

- SEO에 최적화 되어있지 않음
- 초기 페이지로드 속도 느림

<br>

### 2. SSR(Server-Side-Rendering)

---

서버에서 렌더링을 작업하는 렌더링 방식

CSR과 달리 요청에 대한 응답으로 서버의 페이지에 대한 전체 `HTML`을 생성하여 렌더링 해준다. 

<br>

![SSR-process](https://user-images.githubusercontent.com/64825713/117573053-e684fb80-b110-11eb-9d5e-7c0d1d1e06db.png)

<br>

**장점**

- 사용자가 처음으로 컨텐츠를 볼 수 있는 시점이 CSR보다 빠름
- 검색엔진최적화(SEO) 적용에 용이

<br>

**단점**

- 모든 요청에 관해 필요한 부분만 수정하는 것이 아니라 요청이 있을 때마다 완전히 새로운 페이지를 로딩하고 렌더링 해줘야함
- CSR보다 느리고 사용자 경험(UX)이 좋지 않음





<br>

### 3. 언제 사용?

---

그렇다면, CSR과 SSR 둘 중에 어떤 방식으로 웹페이지를 렌더링 하는 것이 좋을까?

조사를 해본 결과, **상황에 따라 적절히 섞어서 사용해주는 것이 좋다**라는 이야기가 제일 많았다. 

둘 중에 딱 하나를 골라서 그것만 사용하는 것이 아니라 수많은 변수와 환경에 맞춰서 적절한 기법을 사용하는 것이 제일 바람직하다는 뜻이다.

<br>

**CSR과 SSR이 사용되면 좋을 상황에 대해서 살펴보자**

- CSR이 좋은 상황
  - SEO(검색 엔진 최적화)가 우선 순위가 아닐 때
  - 유저와의 많은 인터랙션이 필요할 때
  - 웹 애플리케이션을 제작하려고 할 때

<br>

- SSR이 좋은 상황
  - SEO(검색 엔진 최적화)가 최우선 순위일 때, 예를 들어 남들이 검색해서 찾기 쉬운 블로그 운영
  - 빠른 초기 로딩이 필요할 때
  - 유저와의 인터랙션이 많이 필요하지 않을 때

<br>



### 출처

---

https://medium.com/walmartglobaltech/the-benefits-of-server-side-rendering-over-client-side-rendering-5d07ff2cefe8

https://dev.to/alain2020/ssr-vs-csr-2617
