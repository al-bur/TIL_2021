# [210422] CS - Kruskal_알고리즘

### 개념

Kruskal 알고리즘이란 `탐욕적인 방법`을 이용하여 네트워크(간선에 가중치가 존재하는 그래프)의 모든 정점을 최소 비용으로 연결하는 최적해답을 구하는 것이다.

- MST(최소 신장 트리)를 구할 때 Kruskal 알고리즘이 사용된다. 
  - MST(최소 신장 트리)는 그래프 내의 모든 정점을 최소의 비용으로 연결하는 트리이다.단, 최소 신장 트리 내에 사이클이 형성되어서는 안된다는 것이다.

<br>

### 동작

---

1. 그래프의 간선들을 가중치의 오름차순으로 정렬한다.
2. 정렬된 간선 리스트에서 순서대로 사이클을 형성하지 않는 간선을 선택한다.
   - 가장 낮은 가중치를 먼저 선택
   - 사이클을 형성하는 간선은 선택 X
3. 해당 간선을 현재의 MST의 집합에 추가한다.

 <br>

### 다익스트라 vs 크루스칼

---

![다익스트라 vs 크루스칼](https://user-images.githubusercontent.com/64825713/115728542-8c213680-a3bf-11eb-9d7e-eeebf3022fdb.png)

출처:https://buddev.tistory.com/21



### 구현

---

```python
def find_set(element):
    while element != connect_list[element]:
        element = connect_list[element]
    return element
 
def kruskal():
    answer = 0
    for s, e, w in edges_sorted:
        res_s, res_e = find_set(s), find_set(e)
        # union
        if res_s != res_e:
            connect_list[res_e] = res_s
            answer += w
    return answer
 
T = int(input())
for tc in range(1, T + 1):
    # 가중치가 낮은 순으로 정렬
    # 순서대로 findset이 같지 않은 것들을 추가해주는 거지
    # 모든 노드가 visited 된다면 끝내주고
    N, M = map(int, input().split())
    edges = [list(map(int, input().split())) for _ in range(M)]
    edges_sorted = sorted(edges, key=lambda x: x[2])
    # make_set
    connect_list = [x for x in range(N + 1)]
    print('#%d %d' % (tc, kruskal()))
```

