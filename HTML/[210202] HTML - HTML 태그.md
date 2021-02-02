## [210202] HTML 태그

## 1. 주제를 고른 이유에 대하여

---

HTML을 작성하다보니 현재 개발세계에서 convention이 어떻게 구성되어있는 지 알아야겠다는 걸 절실히 느꼈다. 내 방식대로 구조화 하는 것이 아니라 남들이랑 협업할 때도 좋게 convention을 찾아서 보려고 한다.  그리고 오늘 작성해보면서, 자세히 알아보고 싶은 태그들도 몇 개 공식문서를 통해 공부를 하려한다.



### 2. HTML 각 태그 설명 

### 

#### 2.1 

---



#### 2.2 why use form

---

Why do we put `<input>` elements inside of `<form>` elements? For the same reason we put `<li>` tags inside of `<ul>` and `<ol>` elements - it's where they belong. It's *semantically* correct, and helps to define the markup. Parsers, screen readers, and various software can better understand your markup when it is semantically correct - when the markup has meaning, not just structure.

The `<form>` element also allows you to define `method` and `action` attributes, which tell the browser what to do when the form is submitted. AJAX isn't a 100% coverage tool, and as a web developer you should be practicing graceful degradation - forms should be able to be submitted, and data transferred, even when JS is turned off.



sementically correct하니까~

웹사이트의 구조를 훨씬 더 잘 파악할 수 있다네

https://stackoverflow.com/questions/31066693/what-is-the-purpose-of-the-html-form-tag





#### 3. HTML convention 

---

