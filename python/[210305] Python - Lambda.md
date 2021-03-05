## [210305] [Python - Lambda](https://stackabuse.com/lambda-functions-in-python/)

### 1. 주제

---

오늘 알고리즘 수업에서 `lambda`를 접했습니다. `lambda`에 대한 기본적인 지식을 쌓기 위해 `Stack Abuse`라는 사이트에서 정리해 놓은 글을 참고하였습니다!



### 2. What are Lambda Functions?

---

> In Python, we use the `lambda` keyword to declare an anonymous function, which is why we refer to them as "lambda functions". An anonymous function refers to a function declared with no name. Although syntactically they look different, lambda functions behave in the same way as regular functions that are declared using the `def` keyword. The following are the characteristics of Python lambda functions:

파이썬에서, 우리는 `lambda` 키워드를 통해 우리가 편히 `lambda functions`라고 불리는 이름 없는 함수를 선언한다. 이 함수는 아무 이름없이 선언된 함수를 참조한다. 구조상 이 둘은 다르게 보이지만, `lambda functions`들은 `def` 키워드로 선언되는 일반적인 함수들과 같은 방식으로 작동한다. 아래 나오는 특징들은 `lambda functions`의 특징들이다.

<br>

> A lambda function can take any number of arguments, but they contain only a single expression. An expression is a piece of code executed by the lambda function, which may or may not return any value.
>
> Lambda functions can be used to return function objects.
>
> Syntactically, lambda functions are restricted to only a single expression.

- `lambda functions`은 수많은 인자들을 받을 수 있지만, 하나의 표현식만을 가질 수 있다. 표현식이란 `lambda functions`을 사용하여 실행되는 코드 조각이다; 어떠한 값을 반환하거나 반환하지 않을 수 있다.
- `lambda functions` 은 함수 객체들을 반환하는 데 사용된다.
- 구조적으로, `lambda functions`는 오직 하나의 표현식을 가지도록 제한된다.

<br>

### 3. Creating Lambda Function

---

```python
lambda arguement(s) : expression
```

> As stated above, we can have any number of arguments but only a single expression. The lambda operator cannot have any statements and it returns a function object that we can assign to any variable.

위에서 말했듯이, `lambda functions`은 수많은 인자들을 가질 수 있지만 단 하나의 표현식만을 가질 수 있다. `lambda operator`는 아무 조건식도 가질 수 없고 아무 변수에나 할당할 수 있는 함수 객체를 반환한다. 

<br>

```python
remainder = lamdba num: num % 2
print(remainder(5))

## output
# 1
```

>  In this code the `lambda num: num % 2` is the lambda function. The `num` is the argument while `num % 2` is the expression that is evaluated and the result of the expression is returned. The expression gets the modulus of the input parameter by 2. Providing 5 as the parameter, which is divided by 2, we get a remainder of 1. However, despite being anonymous, it was possible for us to call it in the same way that we call a normal function. The statement:

이 코드에서, `lambda num: num % 2`가 `lambda function`이다. `num`이 인자고 `num % 2`가 표현식이고 표현식의 결과값이 반환된다. 표현식은 5라고 입력된 값을 2로 나누어 주고 1이라는 나머지를 반환한다. 비록 익명의 함수이지만, 우리가 일반 함수를 호출해서 사용하는 것처럼 `lambda function`도 가능하다. (아래 예시)

<br>

```python
product = lambda x, y: x * y
print(product(2, 3))

# output
# 6
```

<br>

### 4. Why use Lambda Functions?

---

> Lambda functions are used when you need a function for a short period of time. This is commonly used when you want to pass a function as an argument to higher-order functions, that is, functions that take other functions as their arguments.

`lambda function`은 짧은 시간동안 함수가 필요할 때 사용된다. 함수를 인자로 받는 상위의 함수에서 인자로서 함수를 넘겨주기 위해서 사용된다.

<br>

```python
def testfunc(num):
    return lambda x : x * num

result1 = testfunc(10)

print(result1(9))

# output
# 9
```

<br>



### 5. Conclusion

---

> In Python, a lambda function is a single-line function declared with no name, which can have any number of arguments, but it can only have one expression. Such a function is capable of behaving similarly to a regular function declared using the Python's `def` keyword. Often times a lambda function is passed as an argument to another function

파이썬에서, `lambda function`은 이름 없이 한 줄로 작성된 함수이고 여러 개의 인자를 가질 수 있다. 하지만, 하나의 표현식만 가질 수 있다. 이 함수는 `def` 키워드를 이용하는 일반적인 함수와 비슷하게 작동을 할 수 있다. `lambda function`은 다른 함수의 인자로써 자주 사용되기도 한다.
