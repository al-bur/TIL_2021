# [210220] What is JavaScript? (2)

### 1. 주제를 선택한 이유

---

`front-end 개발자`에게는 `javascript`는 기본이다.  그래서 오늘은  `javascript`가 기본적으로 무엇일까?에 대해서 공부해보았다.

MDN WEB Docs를 참고하였다.

<br>

### 2.  What is JavaScript doing on your page?

>When you load a web page in your browser, you are running your code (the HTML, CSS, and JavaScript) inside an execution environment (the browser tab). This is like a factory that takes in raw materials (the code) and outputs a product (the web page).

<br>

> A very common use of JavaScript is to dynamically modify HTML and CSS to update a user interface, via the Document Object Model API (as mentioned above). Note that the code in your web documents is generally loaded and executed in the order it appears on the page. If the JavaScript loads and tries to run before the HTML and CSS it is affecting has been loaded, errors can occur. You will learn ways around this later in the article, in the [Script loading strategies](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/First_steps/What_is_JavaScript#script_loading_strategies) section.

<br>



#### 2.1 Browser security

---

>Each browser tab has its own separate bucket for running code in (these buckets are called "execution environments" in technical terms) — this means that in most cases the code in each tab is run completely separately, and the code in one tab cannot directly affect the code in another tab — or on another website. This is a good security measure — if this were not the case, then pirates could start writing code to steal information from other websites, and other such bad things.



<br>

>**Third party APIs** are not built into the browser by default, and you generally have to grab their code and information from somewhere on the Web. For example:
>
>- The [Twitter API](https://dev.twitter.com/overview/documentation) allows you to do things like displaying your latest tweets on your website.
>- The [Google Maps API](https://developers.google.com/maps/) and [OpenStreetMap API](https://wiki.openstreetmap.org/wiki/API) allows you to embed custom maps into your website, and other such functionality.

<br>

#### 2.2 JavaScript running order

---

> When the browser encounters a block of JavaScript, it generally runs it in order, from top to bottom. This means that you need to be careful what order you put things in. For example, let's return to the block of JavaScript we saw in our first example:

```javascript
const para = document.querySelector('p');

para.addEventListener('click', updateName);

function updateName() {
  let name = prompt('Enter a new name');
  para.textContent = 'Player 1: ' + name;
}
```

<br>

> Here we are selecting a text paragraph (line 1), then attaching an event listener to it (line 3) so that when the paragraph is clicked, the `updateName()` code block (lines 5–8) is run. The `updateName()` code block (these types of reusable code blocks are called "functions") asks the user for a new name, and then inserts that name into the paragraph to update the display.
>
> If you swapped the order of the first two lines of code, it would no longer work — instead, you'd get an error returned in the [browser developer console](https://developer.mozilla.org/en-US/docs/Learn/Common_questions/What_are_browser_developer_tools) — `TypeError: para is undefined`. This means that the `para` object does not exist yet, so we can't add an event listener to it.

<br>

#### 2.3 Interpreted versus compiled code

---

> You might hear the terms **interpreted** and **compiled** in the context of programming. In interpreted languages, the code is run from top to bottom and the result of running the code is immediately returned. You don't have to transform the code into a different form before the browser runs it. The code is received in its programmer-friendly text form and processed directly from that.
>
> Compiled languages on the other hand are transformed (compiled) into another form before they are run by the computer. For example, C/C++ are compiled into machine code that is then run by the computer. The program is executed from a binary format, which was generated from the original program source code.

<br>

> JavaScript is a lightweight interpreted programming language. The web browser receives the JavaScript code in its original text form and runs the script from that. From a technical standpoint, most modern JavaScript interpreters actually use a technique called **just-in-time compiling** to improve performance; the JavaScript source code gets compiled into a faster, binary format while the script is being used, so that it can be run as quickly as possible. However, JavaScript is still considered an interpreted language, since the compilation is handled at run time, rather than ahead of time.
>
> There are advantages to both types of language, but we won't discuss them right now.





#### 2.4 Server-side versus client-side code

---

> You might also hear the terms **server-side** and **client-side** code, especially in the context of web development. Client-side code is code that is run on the user's computer — when a web page is viewed, the page's client-side code is downloaded, then run and displayed by the browser. In this module we are explicitly talking about **client-side JavaScript**.

<br>

> Server-side code on the other hand is run on the server, then its results are downloaded and displayed in the browser. Examples of popular server-side web languages include PHP, Python, Ruby, ASP.NET and... JavaScript! JavaScript can also be used as a server-side language, for example in the popular Node.js environment — you can find out more about server-side JavaScript in our [Dynamic Websites – Server-side programming](https://developer.mozilla.org/en-US/docs/Learn/Server-side) topic.

<br>

#### 2.5 Dynamic versus static code

---

>The word **dynamic** is used to describe both client-side JavaScript, and server-side languages — it refers to the ability to update the display of a web page/app to show different things in different circumstances, generating new content as required. Server-side code dynamically generates new content on the server, e.g. pulling data from a database, whereas client-side JavaScript dynamically generates new content inside the browser on the client, e.g. creating a new HTML table, filling it with data requested from the server, then displaying the table in a web page shown to the user. The meaning is slightly different in the two contexts, but related, and both approaches (server-side and client-side) usually work together.
>
>A web page with no dynamically updating content is referred to as **static** — it just shows the same content all the time.





