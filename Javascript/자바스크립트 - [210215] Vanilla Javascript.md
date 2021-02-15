# [210215] Vanilla Javascript

### 1. 주제를 선택한 이유

---

`front-end 개발자`에게는 `javascript`는 기본이다. 수많으 `library`와 `frameworks`들이 생겨나고 인기를 얻는 와중에 `javascript` 기본에 대한 중요성도 커지고 있다. 그래서 입문자로써 기본을 공부해보려한다.

공부를 시작하기 전에 `Vanilla Javascript`에 대한 정의와 많은 사람들의 의견을 찾아보고 정리해보았다.

<br>

### 2. [Vanilla Javascript](https://developer.mozilla.org/en-US/docs/Web/HTTP/Overview)

#### 2.1 what is it?

---

>This is a fun question because it can be a bit confusing if English isn’t your first language, or if you’re unfamiliar with US culture.
>
>**It’s about** **ice cream.**
>
>There’s thousands of flavors of ice cream. But the default, defacto, ordinary “flavor” of ice cream is vanilla. If you order “unflavored ice cream” what you’re ordering is vanilla ice cream.
>
>So the concept carries over to JavaScript.
>
>**Vanilla JavaScript is “flavorless JavaScript”**
>
>When you’re trying to draw contrast between JavaScript that uses frameworks and libraries, and JavaScript that *doesn’t* use any at all, we apply the term “vanilla”.
>
>**Is it different from regular JavaScript?**
>
>No. It’s the same. But we typically only use “vanilla” in an effort to show contrast. e.g.
>
>“That’s a really cool app. Did you build it in Vue?”
>
>“Nah. Vanilla js”
>
>[“Nice”](https://www.quora.com/What-is-Vanilla-JavaScript-Is-it-different-from-regular-JavaScript)

`vanilla javascript` 말그대로 `library`나 `framework`를 쓰지 않는 `javascript`라고 보면 된다.

최근 수많은 `library`나 `framework`이 생겨나고 이용되고 있어서 `vanilla javascript`를 강조하는 사람들이 생겨나고 있는 것 같다.


<br>


### 3. Vanilla Javascript 관련 글

#### 3.1 [Is Vanilla JavaScript worth learning? Absolutely](https://www.freecodecamp.org/news/is-vanilla-javascript-worth-learning-absolutely-c2c67140ac34/)

---

>the JavaScript ecosystem is evolving pretty fast
>
>New frameworks are being created. New functionalities are being added to the existing ones. 
>
>In such circumstances, do you still think that knowledge of a particular JavaScript framework is sufficient for a web developer?
>
>Or is it better to understand how the language which all these libraries and frameworks are based on works under the hood?
>
>All the JavaScript frameworks and libraries are inevitably based on its Vanilla core.



자바스크립트 생태계는 굉장히 빠르게 발전하고 있다.

새로운 프레임워크들이 등장하고 있고 새로운 기능들이 기존의 것들에 더해지고 있다.

이러한 상황에서, 특정 자바스크립트 프레임워크에 관한 지식이 웹 개발자에게 충분할 것이라고 생각하는가?

아니면 이러한 라이브러리와 프레임워크의 기본이 되는 언어가 어떻게 작동되는지 이해하는 게 더 좋은가?

모든 자바스크립트 프레임워크와 라이브러리는 불가피하게 순수한 자바스크립트를 기반으로 하고 있다.





![image](https://user-images.githubusercontent.com/64825713/107961286-0791f080-6fe9-11eb-8a46-09bc4f39f8cc.png)


<br>

> There are tons of courses and books about JavaScript and its frameworks. Yet few of them aim to teach you Vanilla JavaScript in a comprehensive way. Most of them specialize for a particular JavaScript technology.
>
> [Eloquent JavaScript](http://eloquentjavascript.net/) will teach you not only basics of JavaScript, but also basics of programming in general. If you are already an advanced developer, this book will provide you a fresh perspective on JavaScript and on its core principles.
>
> 
>
> Another great resource is the book series [You Don’t Know JavaScript](https://github.com/getify/You-Dont-Know-JS) (YDKJS) by Kyle Simpson. Kyle really knows how to teach. His explanations of advanced JavaScript concepts are beginner-friendly and he covers them in-depth.



자바스크립트와 관련 프레임워크를 공부하는 데 수많은 수업과 책들이 있다. 그러나 몇몇의 책들과 강의들만 `vanilla javascript`를 타겟으로 하고있다. 대부분은 특정한 자바스크립트 기술에 집중되어있다.

`Eloquent Javascript`와 `You Don't Know Javascript`를 블로그 저자가 추천해주었다. 


<br>


#### 3.2 [Why you should learn vanilla JavaScript in isolation if you want to be a better developer](https://medium.com/madhash/why-you-should-learn-vanilla-javascript-in-isolation-if-you-want-to-be-a-better-developer-dbc15a7e66bb)

---

>Here are some good reasons why you should learn vanilla JavaScript, even if you think you won’t need to.
>
>Learning vanilla JavaScript is like learning how to build a house from scratch.
>
>Anyone here remembers the good old days of jQuery? No one talks about the once popular JavaScript library anymore. It’s all React and Angular that everyone wants.
>
>

이 글은 왜 사람들이 `Vanilla Javascript`를 배워야하는지 설명을 해준 글이다. 필요없다고 생각해도 읽어보라고 글쓴이는 말한다.

`Vanilla Javascript`를 배우는 것은 스크래치를 이용해서 집을 짓는 방법을 배우는 것과 같다.

`jQuery`의 옛 좋은 시절을 기억하는 사람이 몇이나 있는가? 아무도 인기가 많았던 자바스크립트 라이브러리에 대해서는 이야기를 하지 않는다. 지금은 모두 리액트나 앵귤러를 이야기하고 있다.

<br>

> With a better understanding of how JavaScript works, there is a higher chance that you end up creating higher quality code.
>
> You will be able to see and understand things that 90% of newbie developers don’t see. With this newfound knowledge, you will begin to perceive a set of code differently and see where things can be improved to reduce any necessary complexity.

자바스크립트가 어떻게 작동되는 지에 대하여 이해를 더 잘하게 되면 더 좋은 퀄리티의 코드를 작성할 수 있다.

`vanilla javascript`를 공부하면, 당신은 90퍼센트의 뉴비 개발자들이 보지 못하는 것들을 보고 이해할 수 있다. 이러한 지식을 가지고, 당신은 코드를 다르게 인지할 수 있고 불필요한 복잡함을 줄이면서 코드를 개선할 수 있다.

<br>

>When you learn vanilla JavaScript, your ability to adopt new frameworks and libraries triples in speed. This is because you’re able to look at a piece of code and understand what it means.
>
>The difference between those who know and understand JavaScript and those who don’t is the difference between being a mechanic and being a driver. If your car breaks down, the mechanic would have a higher chance of fixing the car than the driver on their own.

`vanilla javascript`를 공부하면, 새로운 프레임워크와 라이브러리를 배우는 능력의 속도가 훨씬 빨라질 것이다. 이것은 코드를 보고 그것이 무슨 의미인지 이해할 수 있기 떄문이다.

자바스크립트를 알고 이해하는 사람과 못하는 사람의 차이는 메카닉과 운전자의 차이이다. 만약, 차가 망가진다면, 메카닉은 차를 고칠 수 있는 확률이 크지만 운전자는 아니다.

<br>

> Frameworks and libraries change but JavaScript is forever.

프레임워크와 라이브러리는 바뀌지만 자바스크립트는 영원하다.

<br>

#### 4. 비고

---

- `front-end` 개발자에게는 여러 라이브러리와 최신 프레임워크 기술을 요구한다. 리액트, 앵귤러, 뷰등 최신 기술을 가지고 있는 지 없는 지가 일을 할 수 있냐 없냐의 갈림길이다.
- 하지만 그렇다고 너무 해당 기술들에만 집중하는 것은 프레임워크가 변하거나 추가될 때 흐름을 따라갈 수 없다고 생각된다. 그래서 `vanilla javascript` 즉, 자바스크립트 그 자체에 대한 공부가 필요해보인다.
- 이번 글을 작성하면서 관련 기술을 배우는 것도 중요하지만 기본이 되는 순수 자바스크립트에 대해 기본적으로 공부해야겠다고 생각한다.
