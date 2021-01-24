## [210121] Tuple에 대하여

### 1. 주제를 고른 이유에 대하여

---

파이썬으로 기초 문제들을 풀면서 `Tuple`이라는 자료형이 정말 많이 쓰이는 것을 알 수 있었습니다.

많이 쓰이지만 본인은 잘 모르기 때문에 적절하게 `Tuple`을 사용할 수 없어서 이번 주제는 `Tuple`에 대해서 공부해보려고 합니다.



### 2. Tuple이란?

#### 2.1 [python documentation](https://docs.python.org/3/tutorial/datastructures.html)

---

> A tuple consists of a number of values separated by commas, for instance:
>
> ##### code exampe1
>
> ```
> >>> t = 12345, 54321, 'hello!'
> >>> t[0]
> 12345
> >>> t
> (12345, 54321, 'hello!')
> >>> # Tuples may be nested:
> ... u = t, (1, 2, 3, 4, 5)
> >>> u
> ((12345, 54321, 'hello!'), (1, 2, 3, 4, 5))
> >>> # Tuples are immutable:
> ... t[0] = 88888
> Traceback (most recent call last):
> File "<stdin>", line 1, in <module>
> TypeError: 'tuple' object does not support item assignment
> >>> # but they can contain mutable objects:
> ... v = ([1, 2, 3], [3, 2, 1])
> >>> v
> ([1, 2, 3], [3, 2, 1])
> ```
>
> As you see, on output tuples are always enclosed in parentheses, so that nested tuples are interpreted correctly; they may be input with or without surrounding parentheses, although often parentheses are necessary anyway (if the tuple is part of a larger expression). It is not possible to assign to the individual items of a tuple, however it is possible to create tuples which contain mutable objects, such as lists.
>
> Though tuples may seem similar to lists, they are often used in different situations and for different purposes. Tuples are [immutable](https://docs.python.org/3/glossary.html#term-immutable), and usually contain a heterogeneous sequence of elements that are accessed via unpacking (see later in this section) or indexing (or even by attribute in the case of [`namedtuples`](https://docs.python.org/3/library/collections.html#collections.namedtuple)). Lists are [mutable](https://docs.python.org/3/glossary.html#term-mutable), and their elements are usually homogeneous and are accessed by iterating over the list.
>
> A special problem is the construction of tuples containing 0 or 1 items: the syntax has some extra quirks to accommodate these. Empty tuples are constructed by an empty pair of parentheses; a tuple with one item is constructed by following a value with a comma (it is not sufficient to enclose a single value in parentheses). Ugly, but effective. For example:
>
> ##### code exampe2
>
> ```
> >>> empty = ()
> >>> singleton = 'hello',    # <-- note trailing comma
> >>> len(empty)
> 0
> >>> len(singleton)
> 1
> >>> singleton
> ('hello',)
> ```
>
> The statement `t = 12345, 54321, 'hello!'` is an example of *tuple packing*: the values `12345`, `54321` and `'hello!'` are packed together in a tuple. The reverse operation is also possible:
>
> \>>>
>
> ```
> >>> x, y, z = t
> ```
>
> This is called, appropriately enough, *sequence unpacking* and works for any sequence on the right-hand side. Sequence unpacking requires that there are as many variables on the left side of the equals sign as there are elements in the sequence. Note that multiple assignment is really just a combination of tuple packing and sequence unpacking.



#### 2-2 자가 번역

---

이번에도 python document를 번역해보려한다.

완벽하게 의미하는 대로 번역하지는 못하겠지만, 그래도 최대한 작성된 뜻대로 번역을 해보도록 노력하겠습니다😊



`tuple`은 콤마로 나누어진 수많은 값들로 구성되어있다. `code example1`을 보면 알 수 있듯이  `tuple`의 output은 항상 괄호로 둘러쌓여 있고, 그렇기 때문에 interpreted 될 수 있다; `입력값`이 괄호가 있을 수도 있고 없을 때도 있는데 대부분 괄호가 필요하다( `tuple`이 사이즈 가 큰 표현식의 일부분이라면)

`tuple`내 각각의 요소들에게 할당을 하는 것은 불가능 한데 `lists`같은 `mutable objects`를 포함한 `tuple`은 생성가능하다.

`tuple`이 `lists`와 비슷하게 보여도, 각각은 서로 다른 상황, 다른 목적하에 사용이 된다. `tuple`은 `immutable`이  서로 다른 종의 `sequence` 요소들을 포함하고 있는데 이 요소들은  `unpacking`또는 `indexing`을 통해서 접근한다. `Lists`는 `mutable`하고 요소들은 동종의 요소들이고 `Lists`에서 반복을 돌면서 이들에게 접근할 수 있다.

`tuple`의 문제점은 `0` 또는 `1`개의 요소들을 가지고 있는 `tuple`을 생성할 때인데, 이를 가능하게 하기 위해서 `tuple`의 `syntax`는 추가적인 특징들을 가지고 있다. 비어있는 `tuple`은 괄호로 둘러쌓여있는 비어있는 `pair`로 만들어진다. 하나의 요소만을 `tuple`이 가지고 있다면 `comma`와 함께 `tuple`을 구성하게 된다. 

```python
>>> x, y, z = t
```

이런 식으로도 t라는 `tuple`을 만들 수 있는데 이것을 `sequence unpacking`이라고 한다.  `sequnce unpacking`이 가능하려면 상기 `x, y, z  = t`에서 x, y, z라는 3개의 변수들과 동일하게 `t`에도 3개의 요소들이 존재해야한다.



### 3. [Why are there separate tuple and list data types?](https://docs.python.org/3/faq/design.html#id19)

---

`Tuple은 도대체 왜 만들어졌나?`라는 의문을 가지고 python documentation에서 관련 자료를 찾아보았습니다.

제목에 걸려있는 링크는 `list`라는 데이터 타입이 있는데 왜 굳이 `tuple`을 만들어서 서로 구분지어 놨을까에 대한 내용입니다.



서로 많이 닮은 `Lists`와 `tuples`은 기본적으로 다른 방식으로 사용됩니다.

`tuple`은 `Pascal recodes` 또는 `C structs`와 비슷하다고 생각하면 될 것 같습니다; 서로 관련된 데이터들의 집합인데 데이터들은 서로 다른 타입이지만 같은 그룹으로 작동이 된다. 예를 들어, 데카르트 좌표계는 2개 또는 3개의 숫자들로 구성된 `tuple`로서 표현되기에 적절하다.

그런데, `Lists`는 다른 언어에서 쓰이는 배열과 비슷한 느낌이다. 변화하는 요소들을 가지고 있고 이런 요소들은 동일한 타입이고 한개 한개씩 실행된다. 

예를 들어, `os.listdir('.')`은 `string`으로 구성된 리스트를 반환하게 되는데 이는 현재 디렉토리에 있는 파일들을 표시한다. 

`tuples`은 `immutable`하다; `tuple`이 한 번 생성되기 되면 포함되어 있는 요소들이 새로운 값으로 교체 될 수 없다.

반대로, `Lists`는 `mutable`하다; 언제나 요소들을 바꿀 수 있다. `dictionary`의 `key값`으로는 `immutable`한 요소들밖에 쓸 수 없기 때문에 `tuple`만 사용된다.



** 추가적으로, `tuple`에 관해서 많은 웹서핑 도중 많이 나왔던 것에 대해서 짧게 적어보려고 합니다.

`tuple`의 요소들은 `immutable`하기 때문에 정말 변하지 않아야하는 정보들을 담는 데 사용한다. 추후에 고객들의 정보, 변하지 않아야 하는 정보를 담는 데 사용해야겠다.


