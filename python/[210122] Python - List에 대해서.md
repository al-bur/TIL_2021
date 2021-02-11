## [210125] List에 대하여

### 1. 주제를 고른 이유에 대하여

---

파이썬으로 기초 문제들을 풀면서 `List`라는 자료형이 정말 많이 쓰이는 것을 알 수 있었습니다.

이번 주제는 `List`에 대해서 공부해보려고 합니다.



### 2. List란?

#### 2.1 [python documentation](https://docs.python.org/3/tutorial/datastructures.html)

---

> Python knows a number of *compound* data types, used to group together other values.
>
> The most versatile is the *list*, which can be written as a list of comma-separated values (items) between square brackets. Lists might contain items of different types, but usually the items all have the same type.
>
> Like strings (and all other built-in [sequence](https://docs.python.org/3/glossary.html#term-sequence) types), lists can be indexed and sliced:
>
> All slice operations return a new list containing the requested elements. This means that the following slice returns a [shallow copy](https://docs.python.org/3/library/copy.html#shallow-vs-deep-copy) of the list:
>
> Lists also support operations like concatenation:
>
> Unlike strings, which are [immutable](https://docs.python.org/3/glossary.html#term-immutable), lists are a [mutable](https://docs.python.org/3/glossary.html#term-mutable) type, i.e. it is possible to change their content:
>
> You can also add new items at the end of the list, by using the `append()` *method* (we will see more about methods later):
>
> Assignment to slices is also possible, and this can even change the size of the list or clear it entirely:
>
> ```python
> >>> letters = ['a', 'b', 'c', 'd', 'e', 'f', 'g']
> >>> letters
> ['a', 'b', 'c', 'd', 'e', 'f', 'g']
> >>> # replace some values
> >>> letters[2:5] = ['C', 'D', 'E']
> >>> letters
> ['a', 'b', 'C', 'D', 'E', 'f', 'g']
> >>> # now remove them
> >>> letters[2:5] = []
> >>> letters
> ['a', 'b', 'f', 'g']
> >>> # clear the list by replacing all the elements with an empty list
> >>> letters[:] = []
> >>> letters
> []
> ```
>
> The built-in function [`len()`](https://docs.python.org/3/library/functions.html#len) also applies to lists:
>
> It is possible to nest lists (create lists containing other lists), for example:
>
> ```python
> >>> a = ['a', 'b', 'c']
> >>> n = [1, 2, 3]
> >>> x = [a, n]
> >>> x
> [['a', 'b', 'c'], [1, 2, 3]]
> >>> x[0]
> ['a', 'b', 'c']
> >>> x[0][1]
> 'b'
> ```

#### 2.1 추가 설명 (how Lists may be constructed?)

---

- *class* `list`([*iterable*])

  Lists may be constructed in several ways:Using a pair of square brackets to denote the empty list: `[]`Using square brackets, separating items with commas: `[a]`, `[a, b, c]`Using a list comprehension: `[x for x in iterable]`Using the type constructor: `list()` or `list(iterable)`The constructor builds a list whose items are the same and in the same order as *iterable*’s items. *iterable* may be either a sequence, a container that supports iteration, or an iterator object. If *iterable* is already a list, a copy is made and returned, similar to `iterable[:]`. For example, `list('abc')` returns `['a', 'b', 'c']` and `list( (1, 2, 3) )` returns `[1, 2, 3]`. If no argument is given, the constructor creates a new empty list, `[]`.Many other operations also produce lists, including the [`sorted()`](https://docs.python.org/3/library/functions.html#sorted) built-in.Lists implement all of the [common](https://docs.python.org/3/library/stdtypes.html#typesseq-common) and [mutable](https://docs.python.org/3/library/stdtypes.html#typesseq-mutable) sequence operations. 







#### 2.2 번역

---

**(1) python documentation**

파이썬은 다른 값들을 같이 그룹 지어주는 여러 compound 자료형을 가지고 있다. 가장 유연한 자료형은 `list`형이고 `,(콤마)`로 나눠진 값들의 리스트를`[]`로 감싸서 표현된다. `Lists`는 다른 유형의 항목들을 담는데, 대부분 같은 유형의 항목들을 담는다.

다른 `built-in-sequence 유형`의 자료형들과 같이 `Lists`는 인덱싱과 슬라이싱이 가능하다.

모든 슬라이싱은 요구된 요소들을 가지고 있는 새로운 `list`를 반환한다; 이 슬라이싱 작업을 통해서 `list`의 `shallow copy`를 반환한다.

`Lists`는 또한 `concatenation(이어붙이기)`같은 기능도 제공한다.

`strings`자료형과 달리, `Lists`는 변형이 가능한 자료형이다. ex) 가지고 있는 내용물을 바꿀 수 있다는 뜻이다.

`append()`를 사용해서 `list`의 끝에 새로운 항목들을 추가할 수 있다.

슬라이싱을 이용해서 기존 `list`에 값들을 대입도 시켜줄 수 있다. `list`의 크기 자체도 바꿔줄 수도 있고 심지어는 아예  `list`의 값들을 없앨 수도 있다.

 **(2) 추가 설명 (how Lists may be constructed?)**

`Lists`는 여러가지 방법으로 만들어진다

- 빈 `list`라는 것을 알려주는`[]`를 사용해서 만든다. `[]`안에 `,(콤마)`로 항목들을 나눠주게된다. 
- `list comprehension`을 사용해서 만들어 준다.
- `type constructor`를 이용해서 만들어준다; `list()` 또는 `list(iterable)`와 같은 `constructor`는 `iterable`이 가지고 있는 순회 가능한 항목들을 바꾸지 않고 같은 순서로 된 `list`를 만들어준다.
  - ** `iterable`은 `sequence(순회반복을 하게 해주는 자료 컨테이너)`이거나 `iterator 객체(iter()와 같이 반복을 돌려주는 객체)`이다.

만약 `iterable`이 이미 하나의 `list`라면, 복사본이 만들어지고 반환이되는데, 이것은 `iterable[:]`과 비슷하다.

예를 들면, `list('abc')`는 `['a', 'b', 'c']`로 반환이되고 `list( (1, 2, 3) )`는 `[1, 2, 3]`이 반환이된다.

어떠한 인자도 주어지지 않는다면, `constructor`가 새로운 빈 `list`를 만든다. 

