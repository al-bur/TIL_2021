# [210421] CS - Dijkstra_알고리즘

### 1. 개념

다익스트라 알고리즘은 다이나믹 프로그래밍을 활용한 대표적인 **최단 경로 탐색 알고리즘**이다.

GPS 소프트웨어 같은 곳에서 자주 쓰이고 있으며, 특정한 하나의 정점에서 다른 모든 정점(node, vertex)로 가는 최단 경로를 알려준다. 음의 간선은 포함할 수 없으며, 현실에는 음의 간선이 존재하지 않기 때문에 현실세계에서 **자주 쓰이는 적합한 알고리즘 중 하나**라고 보면 된다.

<br>

### 2. 작동 과정

---

1. 출발 노드 설정
2. 출발 노드를 기준으로 각 노드의 최소 비용 저장
3. 방문하지 않은 노드 중에서 가장 비용이 적은 노드 선택
4. 해당 노드를 거쳐서 특정한 노드로 가는  경우를 고려하여 최소 비용 갱신
5. 3~4번 반복

<br>

### 3. 구현

---

```python
# AL[ord(s)-97].append((ord(e)-97, int(p)))
transform = {
    'a': 0,
    'b': 1,
    'c': 2,
    'd': 3,
    'e': 4,
    'f': 5
}
def diikstra(start):
    # distance[start] = 0 생략 가능
    # 최솟거리 찾는 문제에 지장없게 충분히 큰수를 저장
    # 시작점으로부터 각 노드까지의 최단 거리 베열
    distance = [0] + [987654322 for _ in range(V)]
    # 방문 표시 배열 생성
    visited = [0] * (V + 1)
    # 시작 노드 방문 표시
    visited[start] = 1
    # start로 부터 연결되있는 node들 거리 기본값 넣어주기
    for start_adj in relations[start]:
        distance[start_adj[0]] = start_adj[1]
    # 정점 - 1만큼만 반복 (이유: 시작점부터 시작점까지의 거리는 이미 0)
    for node in range(V - 1):
        # 현재 정점중에서 가장 가까운 거리 찾기
        for adj in sorted(relations[node], key=lambda x : x[1]):
            # 아직 방문하지 않은
            if not visited[adj[0]]:
                # 가장 짧은 거리에 있는 node 선택
                node = adj[0]
                # 방문 처리
                visited[node] = 1
                for adj2 in relations[node]:
                    node_name, node_distance = adj2
                    distance[node_name] = min(distance[node_name], distance[node] + node_distance)

    return distance

T = int(input())
for tc in range(1, T + 1):
    V, E = map(int, input().split())
    relations = [[] for _ in range(V + 1)]
    # 노드간 edges 생성
    for i in range(E):
        s, e, w = input().split()
        relations[transform[s]].append((transform[e], int(w)))
    print('#%d %s' % (tc, ' '.join(map(str, diikstra(0)))))
```

- 'a', 'b', 'c', 'd'..를 숫자로 바꾸기 위해서 `dict`구조를 이용했는데, ord() - 97을 이용해서도 구할 수 있다.
