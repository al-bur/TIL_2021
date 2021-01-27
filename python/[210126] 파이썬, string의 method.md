## [210126] 파이썬, string의 method

### 1. 주제를 고른 이유에 대하여

---

어제 list의 method를 알아보았고 오늘은 string의 method에 대해서 공부를 해보았다.

오늘 배운 것을 토대로 앞으로 알고리즘 문제를 풀거나 웹개발을 할 때 유용하게 사용해봐야겠다.



### 2.  string의 method

---

> `.count`(*x*)
>
>  total number of occurrences of *x* in *string*

-> 문자열안에 `x`가 얼마나 있는 지 반환



> `.index`(x[, i[, j]])
>
>  index of the first occurrence of *x* in *s*tring (at or after index *i* and before index *j*)

-> 문자열에서 첫 번쨰 `x`의 인덱스를 반환한다. 



> `len(string)`
>
>  length of string

-> 문자열의 길이를 반환한다.



> `[i:j]]`
>
> slice of *s*tring from *i* to *j*

->  string의 i ~ j까지 슬라이싱 한다.



> `.capitalize()`
>
> Return a copy of the string with its first character capitalized and the rest lowercased.

-> 문자열을 복사하여 첫 번째 글자를 대문자로 바꾸고 나머지는 소문자화 시킨 후 반환해준다.



> .`replace`(*old*, *new*[, *count*])
>
> Return a copy of the string with all occurrences of substring *old* replaced by *new*. If the optional argument *count* is given, only the first *count* occurrences are replaced.

-> `old` 문자열을 `new` 문자열로 바꿔준 문자열을 복사해서 반환해준다. 만약 `count` 인자가 주어졌을 때는 `count` 숫자만큼 바꿔준다.



> .split()

->  문자열을 특정한 단위로 나누어 리스트로 반환합니다.

