# [210207] How does the internet work?

### 1. 주제를 선택한 이유

---

웹개발자는 말그대로 웹사이트를 개발하는 사람이다. 웹사이트를 만드는 수단이나 기술들을 연마는 하고 있지만 이것들의 근본인 웹에 대해서 공부를 해야겠다고 생각했다. 

그래서 먼저, `frontend-roadmap`을 통해서 `internet`이 어떻게 동작하는 지 먼저 공부해보았다.

구글링 해본 결과 HP에서 제공하는 정보가 잘 정리되어 있어서 사용예정이다. 

<br>



### 2. [How does the internet work?](https://store.hp.com/us/en/tech-takes/how-does-the-internet-work)

#### 2.1 what is internet?(using packet)

---

인터넷은 서로 연결되어있는 장치들을 통해서 수많은 데이터와 미디어를 전송하는 전세계적인 컴퓨터 네트워크이다.  `Internet Protocol(IP)` 와 `Transport Control Protocol(TCP)` 를 따르는 `packet routing network`을 통해서 작동된다.



![explanation about PACKETS](C:\Users\ssmin\OneDrive\바탕 화면\TIL\[210207조사필요] 네트워크.assets\image-20210207231851472.png)



> 인터넷을 통해서 보내진 데이터를 `메세지`라고 부르는데, `메세지`가 보내지기 전에 `Packets`라고 불리는 작은 조각들로 나눠지게 된다. 


<br>

#### 2.2 IP and TCP

---

`Internet Protocol(IP)`은 인터넷 연결을 통해서 하나의 컴퓨터에서 다른 컴퓨터로 정보를 보내게 되는데 여기서  정보가 어떻게 보내지는지를 관리하는 규칙들이라고 보면 된다. 

예를 들어, 컴퓨터들은 다른 컴퓨터한테 데이터를 보낼 때 꼭 숫자로된 주소(IP ADDRESS)를 넣어줘야한다.

`Transport Control Protocol(TCP)`는  IP와 같이 작동이 되고 데이터 전송이 믿을만한 건지 확인하기 위해서 사용된다.

-> packets 손실 없고 , 데이터 퀄리티에 영향을 줄 수 있는 지연현상도 없이, packets이 적절한 순서로 정렬이 되게 한다.

<br>

#### 2.3 What happens when you surf the internet

---

- STEP 1 : `modem`이나 `router`를 통해서 나의 디바이스가 웹에 연결이 된다. 여기서 `modem`이나 `router`는 디바이스가 전 지구에 있는 다른 네트워크들과 연결될 수 있게 해준다.
  - `router`는 여러 컴퓨터들이 같은 네트워크에 접속하는 것을 허용해줌과 동시에 `modem`은 내가 사용하는 `Internet Service Provider(ISP)`와 연결된다; `ISP`는 케이블이나 DSL 인터넷을 제공한다.
  - 내 개인용 PC는 `Client`라고 불리고 그 반대편은 `server`라고 불린다
  - `Client` 컴퓨터는 `ISP`를 통해서 인터넷에 연결되고 `server`는 바로 인터넷에 직접 연결된다.



- STEP 2: `Uniform Resource Locator(URL)`이라고 알려진 웹 주소를 브라우저에 타이핑한다.



- STEP 3: 내 요청(query)가 처리되고 내 `ISP`에 push된다.
  - 내 `ISP`는 많은 서버들을 보유하고 있는데 이 서버들은 `Network Access Protection(NAP Server) 와 Domain Name Server(DNS) 같은 데이터를 저장하거나 보내주는 역할을 한다. 
  - 내 브라우저는 내가 `DNS`를 통해서 브라우저에 입력한 도메인 이름에 매칭되는 IP 주소를 찾는다.
    - 여기서 `DNS`는 내가 브라우저에 입력한 텍스트 형식의 도메인 주소를 숫자 형식인 IP주소로 변환해준다.



- STEP 4: 브라우저가 `Hypertext Transfer Protocol(HTTP)` 요청을 타겟 서버에 보낸다; `TCP/IP`를 이용하여 웹페이지의 복사본을 클라이언트에게 보내라는 요청
  - `HTTP` : 인터넷 커뮤니케이션에 사용되는 언어
  - `HTTPS` : 보안이 강화된 버전의 `HTTP`, 나의 브라우저와 웹사이트들간의 모든 커뮤니케이션이 암호화된다.



- STEP 5:  `server`가 요청을 승인하고 `200 OK`라는 메세지를 클라이언트 컴퓨터에게 보낸다. 그리고 나서, `server`가 데이터 패킷 형태로 웹페이지 파일들을 브라우저에 보낸다.



- STEP 6: 내 브라우저가 패킷들을 재조합하면서 웹페이지가 로딩이 된다. 끝!






<br>

### 3. 비고

---

이렇게 `How internet works`에 대해서 정말 간단하게 큰 그림을 공부해보았다. `TCP`, `IP`, `Packet` 같은 처음 들어보는 단어들이 아직까지는 생소하다. 오늘은 큰 그림을 보았으니까 앞으로는 세세하게 하나하나씩 공부할 예정이다!
