## [210131] Dictionary에 대하여

### 1. 주제를 고른 이유에 대하여

---

이번에는 `dictionary`에 대해서 공부해보려고 합니다. 

여러 가지 자료형에 대해 공부하다보니 이렇게 계속 하나하나씩 공부하게 되는 것 같습니다.



### 2. Dictionary란?

#### 2.1 [python documentation](https://docs.python.org/3/tutorial/datastructures.html)

---

> Another useful data type built into Python is the *dictionary* (see [Mapping Types — dict](https://docs.python.org/3/library/stdtypes.html#typesmapping)). Dictionaries are sometimes found in other languages as “associative memories” or “associative arrays”. Unlike sequences, which are indexed by a range of numbers, dictionaries are indexed by *keys*, which can be any immutable type; strings and numbers can always be keys. Tuples can be used as keys if they contain only strings, numbers, or tuples; if a tuple contains any mutable object either directly or indirectly, it cannot be used as a key. You can’t use lists as keys, since lists can be modified in place using index assignments, slice assignments, or methods like `append()` and `extend()`.
>
> It is best to think of a dictionary as a set of *key: value* pairs, with the requirement that the keys are unique (within one dictionary). A pair of braces creates an empty dictionary: `{}`. Placing a comma-separated list of key:value pairs within the braces adds initial key:value pairs to the dictionary; this is also the way dictionaries are written on output.
>
> The main operations on a dictionary are storing a value with some key and extracting the value given the key. It is also possible to delete a key:value pair with `del`. If you store using a key that is already in use, the old value associated with that key is forgotten. It is an error to extract a value using a non-existent key.
>
> Performing `list(d)` on a dictionary returns a list of all the keys used in the dictionary, in insertion order (if you want it sorted, just use `sorted(d)` instead). To check whether a single key is in the dictionary, use the [`in`](https://docs.python.org/3/reference/expressions.html#in) keyword.e built-in function [`len()`](https://docs.python.org/3/library/functions.html#len) also applies to lists:
>
> It is possible to nest lists (create lists containing other lists), for example:
>
> Here is a small example using a dictionary:
>
> \>>>
>
> ```
> >>> tel = {'jack': 4098, 'sape': 4139}
> >>> tel['guido'] = 4127
> >>> tel
> {'jack': 4098, 'sape': 4139, 'guido': 4127}
> >>> tel['jack']
> 4098
> >>> del tel['sape']
> >>> tel['irv'] = 4127
> >>> tel
> {'jack': 4098, 'guido': 4127, 'irv': 4127}
> >>> list(tel)
> ['jack', 'guido', 'irv']
> >>> sorted(tel)
> ['guido', 'irv', 'jack']
> >>> 'guido' in tel
> True
> >>> 'jack' not in tel
> False
> ```
>
> The [`dict()`](https://docs.python.org/3/library/stdtypes.html#dict) constructor builds dictionaries directly from sequences of key-value pairs:
>
> \>>>
>
> ```
> >>> dict([('sape', 4139), ('guido', 4127), ('jack', 4098)])
> {'sape': 4139, 'guido': 4127, 'jack': 4098}
> ```
>
> In addition, dict comprehensions can be used to create dictionaries from arbitrary key and value expressions:
>
> \>>>
>
> ```
> >>> {x: x**2 for x in (2, 4, 6)}
> {2: 4, 4: 16, 6: 36}
> ```
>
> When the keys are simple strings, it is sometimes easier to specify pairs using keyword arguments:
>
> \>>>
>
> ```
> >>> dict(sape=4139, guido=4127, jack=4098)
> {'sape': 4139, 'guido': 4127, 'jack': 4098}
> ```



#### 2.2 번역

---

**python documentation**

`dictionary`는 파이썬에 내장된 유용한 자료형이다. `dictionary`는 다른 언어에서 때때로  `연관 메모리(associative memories)` 나 `연관 배열(associative arrays)`의 형태로 쓰이는 것을 볼 수 있다. 숫자를 가지고 인덱싱이 가능한`sequences` 형이라는 달리, `dictionary`는 `keys`에 의해서 인덱싱이 가능하다. `keys`는 어떤 `immutable` 자료형들이 될 수 있다; `strings`이나 `numbers` 모두 `keys`로 사용될 수 있다. `Tuples`도 `keys`로 사용될 수 있는데, 단 `Tuples`이 `strings`, `numbers` 또는 `Tuples`를 가지고 있을 경우만 가능하다;  `tuple`이 직접적으로나 간접적으로 `mutalbe`한 객체를 가지고 있다면, `keys`로서 사용이 불가능하다.

`lists`는 `keys`로서 사용이 불가능한데 그 이유는`lists`가 인덱스 접근, 슬라이싱 접근, `append()`나 `extend()`를 통한 방법으로 값이 수정될 수 있어서다.



`dictionary` 를 `key:value` 쌍들의 집합이라고 보는 게 가장 적절하다. 대신, 여기서 `keys`가 동일 `dictionary`내에서 중복되지 않는다는 제약조건에 맞아야한다. `{}`를 통해서 비어있는 `dictionary`를 만든다. `,(comma)`로 구별된 `key:value`쌍들을 괄호안에 넣어주면 `dictionary`에 초기 `key:value`쌍들이 추가가 된다; 이것이 `dictionary`가 출력되는 방식이다.

`dictionary`에서의 주 연산은 `key`를 이용하여 `value`를 저장하거나 `value`를 추출하는 작업들이다. `del`을 이용해서 `key:value` 쌍을 제거하는 것도 가능하다. 기존의 `key`를 이용해서 `value`를 저장하게 되면,  `key`와 연계돼서 저장되어있던 `value`는 사라지게 된다. 존재하지 않는 `key`를 이용해서 `value`를 추출하려고 하면 에러가 난다.

`dictionary`에 `list(d)`를 사용하게 되면 `dictionary`에 존재하는 모든 `keys`의 리스트가 반환이 된다. (삽입 순서대로)( 만약 정렬을 원하면, `sorted(d)`를 사용하면 된다.) 그리고 `dictionary`내에 하나의 `key`가 존재하는지 체크하고 싶으면 `in` 키워드를 사용하면된다.

<br>

### 3.  [Dictionary의 method](https://www.w3schools.com/python/python_ref_dictionary.asp)

---

> `dictionary.clear()`
>
> removes all the elements from a dictionary

-> `dictionary`내의 모든 요소들은 제거한다.

<br>

> `dictionary.copy()`
>
> returns a copy of the specified dictionary

-> `dictionary`의 복사본을 반환한다.

<br>

> `dict.fromkeys(keys, value)`
>
> returns a dictionary with the specified keys and the specified value

-> 주어진 `keys`와 `value`로 구성된 `dictionary`를 반환한다.

<br>

> `dictionary.get('keyname')`
>
> returns the value of the item with the specified key.

-> 주어진 `key`값의 `value`를 반환한다.

<br>

> `dictionary.pop(keyname, [defaultvalue, )`
>
> removes the specified item from the dictionary
>
> The value of the removed item is the return value of the pop() method

-> `dictionary`에서 주어진 `keyname`을 가지고 있는 `item(항목)`을 제거한다. 제거된 `value`는 반환된다.

<br>

> `dictionary.popitem()`
>
> removes the item that was last inserted into the dictionary
>
> The removed item is the return value of the popitem() method, as a tuple

->  `dictionary`에 마지막으로 삽입된 `item(항목)`을 제거한다. 제거된 `item`이 `tuple`형식으로 반환된다.

<br>

> `dictionary.setdefault(keyname, value)`
>
> returns the value of the item with the specified key
>
> If the key does not exist, insert the key, with the specified value

-> .get()과 비슷한 역활을 한다.

-> `keyname`과 매칭되어있는 `value`를 반환해주는데, 만약 `keyname`이 `dictionary`에 존재하지 않으면 `keyname:value`쌍으로 새롭게 `item`을 생성해준다.

<br>

> `dictionary.update(iterable)`
>
> inserts the specified items to the dictionary
>
> The specified items can be a dictionary, or an iterable object with key value pairs.

-> `dictionary`에 특정한 `items(항목들)`을 삽입해준다.  `items`는 dictionary 또는 `key value`쌍을 가진 순회가능한 객체일 수 도 있다.

<br>

> `dictionary.values()`
>
> returns a view object. The view object contains the values of the dictionary, as a list

-> `dictionary`의 `value`값들을 `list`로 반환해준다.

<br>
