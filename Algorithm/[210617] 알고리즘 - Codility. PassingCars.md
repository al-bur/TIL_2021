# [210617] 알고리즘 - Codility. PassingCars

### 1. 문제설명

---


```markdown
[문제]

A non-empty array A consisting of N integers is given. The consecutive elements of array A represent consecutive cars on a road.

Array A contains only 0s and/or 1s:

0 represents a car traveling east,
1 represents a car traveling west.
The goal is to count passing cars. We say that a pair of cars (P, Q), where 0 ≤ P < Q < N, is passing when P is traveling to the east and Q is traveling to the west.

For example, consider array A such that:

  A[0] = 0
  A[1] = 1
  A[2] = 0
  A[3] = 1
  A[4] = 1
We have five pairs of passing cars: (0, 1), (0, 3), (0, 4), (2, 3), (2, 4).

Write a function:

class Solution { public int solution(int[] A); }

that, given a non-empty array A of N integers, returns the number of pairs of passing cars.

The function should return −1 if the number of pairs of passing cars exceeds 1,000,000,000.

For example, given:

  A[0] = 0
  A[1] = 1
  A[2] = 0
  A[3] = 1
  A[4] = 1
the function should return 5, as explained above.

Write an efficient algorithm for the following assumptions:

N is an integer within the range [1..100,000];
each element of array A is an integer that can have one of the following values: 0, 1.

```

<br>

### 2. 문제풀이

---

```python
​```
아이디어
-> 해당 문제는 효율성 검사도 하는 문제이다 (이중 for문으로는 문제 통과 불가한 상황)
-> for문 하나로 문제를 풀어야함
-> '0' 뒤에 '1'이 몇 개가 나오는 지를 구하는 것이 답인 문제
-> 배열의 모든 '0'에 대하여 '1'의 개수를 구해줘야하기 때문에, for문을 돌면서 '0'을 만날때마다 zero_cnt(현재 0의 개수)를 0의 가중치로 놓고 zero_cnt * 1로 답을 구해주었다
​```


def solution(A):
    passing_cars = 0
    A_length = len(A)
    zero_cnt = 0
    for i in range(A_length):
        if A[i] == 0:
            zero_cnt += 1
            continue
        if zero_cnt and A[i] == 1:
            passing_cars += zero_cnt * 1
            if passing_cars > 1000000000:
                return -1
    else:
        return passing_cars
```
