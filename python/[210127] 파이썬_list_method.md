## [210127] 파이썬_list_method

### 1. 주제를 고른 이유에 대하여

---

오늘은 파이썬에서 많이 쓰이는 list라는 data_structure의 method를 공부해보고 정리해보았다.

알고리즘 같은 문제들을 풀 때 lis 자료형을 많이 사용하기 때문에 이번 기회에 여러 method들을 살펴보려합니다. 

python documentation을 통해 여러 method에 대한 정의와 예시들을 공부했다.



### 2.  [list의 method](https://docs.python.org/3/tutorial/datastructures.html)

---

> `list.append`(*x*)
>
> Add an item to the end of the list. Equivalent to `a[len(a):] = [x]`.

-> 리스트 끝에 항목을 추가한다.

<br>

> `list.extend`(*iterable*)
>
> Extend the list by appending all the items from the iterable. Equivalent to `a[len(a):] = iterable`.

-> extend 또한 append와 같이 리스트 끝에 항목을 추가합니다. 근데, append와 다른 점은 extend는 iterable하게 추가한다는 점

ex) string = 'app'을 list.extend(string)을 해주게되면 -->  list = ['a', 'p', 'p']로 추가가되고

append(string)을 해주게 되면 -> list = ['app']으로 추가가 되는 차이가 있습니다.

<br>

> `list.insert`(*i*, *x*)
>
> Insert an item at a given position. The first argument is the index of the element before which to insert, so `a.insert(0, x)` inserts at the front of the list, and `a.insert(len(a), x)` is equivalent to `a.append(x)`.

-> 항목을 원하는 위치에 삽입을 해준다. 첫 번째 `i`인자는 요소를 삽입하기 `전`에 위치한 인덱스를 가리킵니다.

<br>

> `list.remove`(*x*)
>
> Remove the first item from the list whose value is equal to *x*. It raises a [`ValueError`](https://docs.python.org/3/library/exceptions.html#ValueError) if there is no such item.

-> `list`에서 인자 `x`와 동일한 가장 첫 번째 값을 삭제 해준다. 만약에 일치하는 값이 없으면 `ValueError`를  발생시킵니다.

<br>

> `list.pop`([*i*])
>
> Remove the item at the given position in the list, and return it. If no index is specified, `a.pop()` removes and returns the last item in the list. (The square brackets around the *i* in the method signature denote that the parameter is optional, not that you should type square brackets at that position. You will see this notation frequently in the Python Library Reference.)

-> 주어진 인자 `i`에 해당하는 인덱스의 항목을 삭제한 후 삭제된 값을 반환합니다. 인덱스가 지정되 있지 않으면 리스트의 마지막 항목을 제거하고 반환해준다. 

`i`인자는 필수 요소가 아닌 `optional`입니다.

<br>

> `list.clear`()
>
> Remove all items from the list. Equivalent to `del a[:]`.

-> `list`에 있는 모든 항목들을 제거합니다.

<br>

> `list.index`(*x*[, *start*[, *end*]])
>
> Return zero-based index in the list of the first item whose value is equal to *x*. Raises a [`ValueError`](https://docs.python.org/3/library/exceptions.html#ValueError) if there is no such item.The optional arguments *start* and *end* are interpreted as in the slice notation and are used to limit the search to a particular subsequence of the list. The returned index is computed relative to the beginning of the full sequence rather than the *start* argument.

-> 인자 `x`와 같은 값을 가지는 첫 번째 항목을 리스트에서 반환합니다. 만약 만족하는 값이 없다면 `ValueError`를 반환합니다. 선택적 인자인 `start`와 `end`는 슬라이스 notation으로 해석되고 특정한 시퀀스를 리스트에서 추출할 때 사용됩니다. 

<br>

> `list.``count`(*x*)
>
> Return the number of times *x* appears in the list.

-> `list`에서 인자 `x`가 몇 번 등장하는 지에 대한 값을 반환한다.

<br>

> `list.``sort`(***, *key=None*, *reverse=False*)
>
> Sort the items of the list in place (the arguments can be used for sort customization, see [`sorted()`](https://docs.python.org/3/library/functions.html#sorted) for their explanation).

-> 리스트 내 항목들을 정렬한다. (인자들은 sort를 커스터마이즈 할 수 있다.)

<br>

> `list.``reverse`()
>
> Reverse the elements of the list in place.

-> 리스트의 요소들을 제자리에서 뒤집는다.

<br>

> `list.``copy`()
>
> Return a shallow copy of the list. Equivalent to `a[:]`

-> 리스트의 얕은 복사값을 반환합니다.
