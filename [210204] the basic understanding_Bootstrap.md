## [210204] the basic understanding_Bootstrap 

### 1. 주제를 고른 이유에 대하여

---

`CSS`와 `HTML`을 공부하는 중이다. 구조화를 계속 해보는 연습을 하고 싶어서  `CSS Framework`중 하나인 `Bootstrap`을 사용을 해보면서 여러번 실습을 해보았다. 

공부를 하면서 `CSS`나 `html`의 구조에 대해서 공부도 해보고 `layout`을 짜기도 해봤는데 새로 알게 된 Bootstrap에 대한 정보를 기록을 해보면서 다시 한 번 내용을 정리해보려고 한다.

자주 쓰는 component를 위주로 정리해보았다.



### 2. Bootstrap 시작하기

먼저, html에서 bootstrap을 이용해주기 위해 

https://getbootstrap.com/docs/5.0/getting-started/introduction/ 이 url에서

`Bootstrap` 에서 제공하는 `class`들을 사용하기 위해서 `CSS` 와 `JS` 소스를 `cdn`방식으로 사용한다.

> cdn이란 콘텐츠 전송 네트워크라는 뜻으로 콘텐츠를 효율적으로 전달하기 위해 여러 노드를 가진 네트워크에 데이터를 저장하여 제공하는 시스템을 말한다. 인터넷 서비스 제공자에 직접 연결되어 데이터를 전송하므로, 콘텐츠 병목을 피할 수 있는 장점이 있다.



```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Document</title>
  <!-- Bootstrap에서 제공하는 CSS 소스들을 받아오기 위한 링크 -->
  <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/bootstrap@5.0.0-beta1/dist/css/bootstrap.min.css" rel="stylesheet" integrity="sha384-giJF6kkoqNQ00vy+HMDP7azOuL0xtbfIcaT9wjKHr8RbDVddVHyTfAAsrekwKmP1" crossorigin="anonymous">
</head>
<body>
   <!-- Bootstrap에서 제공하는 Javascript 소스들을 받아오기 위한 링크 -->
  <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.0.0-beta1/dist/js/bootstrap.bundle.min.js" integrity="sha384-ygbV9kiqUc6oa4msXn9868pTtWMgiQaeYH7/t7LECLbyPA2x65Kgf80OJFdroafW" crossorigin="anonymous"></script>
</body>
</html> 
```

상기는 bootstrap 링크를 불러온 html의 모습이다.





#### 3. Component

---

##### 3.1 Carousel

> A slideshow component for cycling through elements—images or slides of text—like a carousel.
>
> The carousel is a slideshow for cycling through a series of content, built with CSS 3D transforms and a bit of JavaScript. It works with a series of images, text, or custom markup. It also includes support for previous/next controls and indicators.

```html
<div id="carouselExampleControls" class="carousel slide" data-bs-ride="carousel">
  <div class="carousel-inner">
    <div class="carousel-item active">
      <img src="..." class="d-block w-100" alt="...">
    </div>
    <div class="carousel-item">
      <img src="..." class="d-block w-100" alt="...">
    </div>
    <div class="carousel-item">
      <img src="..." class="d-block w-100" alt="...">
    </div>
  </div>
  <a class="carousel-control-prev" href="#carouselExampleControls" role="button" data-bs-slide="prev">
    <span class="carousel-control-prev-icon" aria-hidden="true"></span>
    <span class="visually-hidden">Previous</span>
  </a>
  <a class="carousel-control-next" href="#carouselExampleControls" role="button" data-bs-slide="next">
    <span class="carousel-control-next-icon" aria-hidden="true"></span>
    <span class="visually-hidden">Next</span>
  </a>
</div>
```

![image-20210204094207250](C:\Users\ssmin\OneDrive\바탕 화면\TIL\[조사필요] Bootstrap.assets\image-20210204094207250.png)

with controls 예시다.







##### 3.1 Grid Card



##### 3.2 Pagination

> Documentation and examples for showing pagination to indicate a series of related content exists across multiple pages.

```html
<nav aria-label="Page navigation example">
  <ul class="pagination">
    <li class="page-item"><a class="page-link" href="#">Previous</a></li>
    <li class="page-item"><a class="page-link" href="#">1</a></li>
    <li class="page-item"><a class="page-link" href="#">2</a></li>
    <li class="page-item"><a class="page-link" href="#">3</a></li>
    <li class="page-item"><a class="page-link" href="#">Next</a></li>
  </ul>
</nav>
```

![image-20210204101759071](C:\Users\ssmin\OneDrive\바탕 화면\TIL\[조사필요] Bootstrap.assets\image-20210204101759071.png)



##### 3.4 Button

> button styles for actions in forms, dialogs, and more with support for multiple sizes, states, and more.

```html
<a class="btn btn-primary" href="#" role="button">Link</a>
<button class="btn btn-primary" type="submit">Button</button>
<input class="btn btn-primary" type="button" value="Input">
<input class="btn btn-primary" type="submit" value="Submit">
<input class="btn btn-primary" type="reset" value="Reset">
```

![image-20210204094924871](C:\Users\ssmin\OneDrive\바탕 화면\TIL\[조사필요] Bootstrap.assets\image-20210204094924871.png)example



##### 3.3 Modal

> Use Bootstrap’s JavaScript modal plugin to add dialogs to your site for lightboxes, user notifications, or completely custom content.

모달은 ~ 





##### 3.3.1 ex)Live demo

Toggle a working modal demo by clicking the button below. It will slide down and fade in from the top of the page.

해당 기능은 자주 쓰이는 기능이다.



![image-20210204094535195](C:\Users\ssmin\OneDrive\바탕 화면\TIL\[조사필요] Bootstrap.assets\image-20210204094535195.png)

```html
  <h2 class="text-center">Modal</h2>
  <!-- Button trigger modal -->
  <!-- data-bs-target값이 modal의 id값과 동일해야한다. -->
  <button type="button" class="btn btn-primary" data-bs-toggle="modal" data-bs-target="#exampleModal">
    Launch demo modal
  </button>

  <!-- Modal -->
  <!-- 여기의 id값과 data-bs-target의 값과 동일해야한다. -->
  <div class="modal fade" id="exampleModal" tabindex="-1" aria-labelledby="exampleModalLabel" aria-hidden="true">
    <div class="modal-dialog">
      <div class="modal-content">
        <div class="modal-header">
          <h5 class="modal-title" id="exampleModalLabel">This is Modal</h5>
          <button type="button" class="btn-close" data-bs-dismiss="modal" aria-label="Close"></button>
        </div>
        <div class="modal-body">
          ...
        </div>
        <div class="modal-footer">
          <button type="button" class="btn btn-secondary" data-bs-	 dismiss="modal">Close</button>
          <button type="button" class="btn btn-primary">Save changes</button>
        </div>
      </div>
    </div>
  </div>
```



### 3. 느낀점

---

Bootstrap의 기능들끼리 조합해서 만들 수 있다.

하나의 기능만을 구현하는 것이 아니라 grid card에 pagination을 삽입한 다 던지 그런 식으로 진행하면될듯

아마 추후에 레이아웃을 짜거나 빨리 웹사이트를 만들어야하는 상황이 있을 거니까 `bootstrap`을 사용해보면서 해보면 좋을 것 같다.





#### ** 직접 해본 것

![image-20210204103948188](C:\Users\ssmin\OneDrive\바탕 화면\TIL\[조사필요] Bootstrap.assets\image-20210204103948188.png)





```html
<!DOCTYPE html>
<html lang="ko">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <link rel="stylesheet" href="style.css">
  <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.0.0-beta1/dist/css/bootstrap.min.css" rel="stylesheet" integrity="sha384-giJF6kkoqNQ00vy+HMDP7azOuL0xtbfIcaT9wjKHr8RbDVddVHyTfAAsrekwKmP1" crossorigin="anonymous">
  <title>Document</title>
</head>
<body>
  <div class="container-fluid container-md">
    <!-- 1. Nav -->
    <!-- nav를 flexbox로 설정해주고 between으로 서로 양옆으로 보내줌 -->
    <nav class="d-flex sticky-top bg-dark justify-content-between">
        <a href="#">
          <img src="images/logo.png" alt="Logo Image">
        </a>
        <!-- 왜 nav에 d-flex가 있는데 ul에 상속이 안되죠? -->
        <!-- 그래서 따로 flex-box로 설정해주고 row로 해주고 중앙정렬해줌 -->
        <ul class="d-flex flex-row align-items-end">
          <li class="me-4"><a href="#" class="text-white text-decoration-none">Home</a></li>
          <li class="me-4"><a href="#" class="text-white text-decoration-none">Community</a></li>
          <li class="me-4"><a href="#" class="text-white text-decoration-none">Login</a></li>
        </ul>
    </nav>

    <!-- 2. Header -->
    <header class="d-flex flex-column align-items-center justify-content-center">
        <div class="display-1 text-white fw-bolder">Cinema</div>
        <div class="display-1 text-white fw-bolder">Community</div>
        <a href="https://www.youtube.com/" class="btn btn-primary btn-lg mt-4">Let's Go</a>
    </header>

    <!-- 3. Section -->
    <!-- 여기서 align-items-center를 하게되면 <article>에서 또 justify-content-center -->
    <!-- 를 적용하려해도 안되기 때문에 section에서는 정렬하지 않는다 -->
    <section class="d-flex flex-column">
      <!-- 그래서 텍스트만 정렬해준다 -->
      <h2 class="mt-3 mb-5 fw-bold text-center">Used Skills</h2>
      <!-- 왜 여기서 또 d-flex를 써줘야하는가? -->
      <article class="d-flex flex-row justify-content-around flex-wrap">
        <div>
          <!-- p는 div안에 존재하기 때문에 div를 기준으로 center해준다 -->
          <img src="images/web.png" alt="Web Image">
          <p class="text-center">Web</p>
        </div>
        <div>
          <img src="images/html5.png" alt="HTML5 Image">
          <p class="text-center">HTML5</p>
        </div>
        <div>
          <img src="images/css3.png" alt="CSS3 Image">
          <p class="text-center">CSS3</p>
        </div>
      </article>
    </section>

    <!-- 4. Footer -->
    <footer class="d-flex fixed-bottom bg-primary justify-content-center text-white align-items-end">
      <p>HTML & CSS project. Created by SSM</p>
    </footer>
  </div>
  <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.0.0-beta1/dist/js/bootstrap.bundle.min.js" integrity="sha384-ygbV9kiqUc6oa4msXn9868pTtWMgiQaeYH7/t7LECLbyPA2x65Kgf80OJFdroafW" crossorigin="anonymous"></script>
</body>
</html>

```

https://cdn.jsdelivr.net/npm/bootstrap@5.0.0-beta1/dist/css/bootstrap.css

이것을 통해서 bootstrap의 css class를 세부적으로 볼 수 있다.

!important가 상속되는 관계에서 맨 하위로 밀린다.
