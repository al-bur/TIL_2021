## [210120] 파이썬, The 'return' statement에 대해서

### 1. 주제를 고른 이유에 대하여

---

파이썬을 공부하던 와중에 '함수'라는 챕터를 공부하게 되었습니다. 함수에 대해서 공부를 하다보니 난데없이 return값이 많이 나오기 시작했습니다. return이라는 개념이 함수내에서 값을 반환한다는 것인지는 알겠는데 더 자세하게 알아야 겠다고 생각했습니다.

앞으로 함수를 많이 사용하게 될텐데 return에 대해서 좀 더 공부해야겠다고 생각해서 오늘의  TIL은  `'the return statement'`로 하게 되었습니다  



### 2. What is the return statement? (Python documentation)

---

아무래도 프로그래밍 언어도 언어이다 보니까 많은 함수, 메서드, 식별자등등이 각 언어마다 규칙으로 정해져있다.

그래서 파이썬의 `return` 에 대해서 알기 위해서는 공식 문서를 번역해보는 것도 좋을 것 같아서 해보았습니다.

#### 2.1 원본

---

> ```
> return_stmt ::=  "return" [expression_list]
> ```
>
> [`return`](https://docs.python.org/3/reference/simple_stmts.html#return) may only occur syntactically nested in a function definition, not within a nested > class definition.
>
> If an expression list is present, it is evaluated, else `None` is substituted.
>
> [`return`](https://docs.python.org/3/reference/simple_stmts.html#return) leaves the current function call with the expression list (or `None`) as return value.
>
> When [`return`](https://docs.python.org/3/reference/simple_stmts.html#return) passes control out of a [`try`](https://docs.python.org/3/reference/compound_stmts.html#try) statement with a [`finally`](https://docs.python.org/3/reference/compound_stmts.html#finally) clause, that `finally` clause is executed before really leaving the function.
>
> In a generator function, the [`return`](https://docs.python.org/3/reference/simple_stmts.html#return) statement indicates that the generator is done and will cause [`StopIteration`](https://docs.python.org/3/library/exceptions.html#StopIteration) to be raised. The returned value (if any) is used as an argument to construct [`StopIteration`](https://docs.python.org/3/library/exceptions.html#StopIteration) and becomes the `StopIteration.value` attribute.
>
> In an asynchronous generator function, an empty [`return`](https://docs.python.org/3/reference/simple_stmts.html#return) statement indicates that the asynchronous generator is done and will cause [`StopAsyncIteration`](https://docs.python.org/3/library/exceptions.html#StopAsyncIteration) to be raised. A non-empty `return` statement is a syntax error in an asynchronous generator function.
>
> [출처: python documentaton](https://docs.python.org/3/reference/simple_stmts.html)



#### 2.2 자가 번역

---

`return` 은 문법 구조상으로 함수 정의안에서` nested`<함수정의 안에서만 기능>하게 일어난다. (class보다는 작은 범위)

표현식이 존재할 때, 값으로 변환될 수 있지만 존재하지 않으면 `None`값으로 대체 된다.

*표현식 : 값으로 변화될 수 있는 문장

`return`은 표현식과 함께 현재 호출된 함수에서 떠난다.

`return`이 `finally clause`와 함께 `try statement`의 통제권을 벗어났을 때, 그 `finally clause`는 정말로 함수를 떠나기전에 실행된다.

`generator 함수`에서, `return`문은 generator가 실행됐고 `StopIteration`이 실행될 것이다라고 알려준다. 반환된 값은 `StopIteration`을 구축하기 위한 인자로 사용되고 그것의 value가 된다.

`비동기 generator함수`에서, 빈 `return`문은 `비동기 generator`가 작동했다는 것을 뜻하고 `StopAsyncIteration`이 raise된다. 비어있지 않은 `return`문은 비동기 `generator 함수`에서 sytax error이다. 



* generator 함수 == iterator를 생성해주는 함수

* finally clause == 무슨 일이 있던지 실행 되는 절



상기 번역본은 지속적으로 다듬어 나갈 예정입니다. 

아직까지는 지식이 많이 없어 해석을 자세히 할 수 없었고 앞으로 더욱 다듬어 가겠습니다



### 3. print vs return

---

`jupyter notebook`으로 코딩을 하다보면 print()와 return을 사용하면 둘 다 값을 출력하는 것처럼 보인다.

1. print() 사용

![image-20210121231203913](C:\Users\ssmin\OneDrive\바탕 화면\[20210120] 파이썬, The 'return' statement에 대해서.assets\image-20210121231203913.png)

2. return 사용

![image-20210121231215863](C:\Users\ssmin\OneDrive\바탕 화면\[20210120] 파이썬, The 'return' statement에 대해서.assets\image-20210121231215863.png)



이렇게 보면 둘 다 print라는 것을 출력하는 것처럼 보인다. 하지만 차이점은 분명히 있다. 

print()는 정말로 보여주기 위해 출력을 하는 것이고 return은 출력은 하지 않고 a라는 값을 반환하는 것이다.

return 또한 출력하는 것처럼 보이지만 `Out[11]`이라고 적혀있는 것을 보면 반환한다라는 것을 알 수 있다.
