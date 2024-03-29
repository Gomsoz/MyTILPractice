그래프의 표현 방식
-----
### 인접 행렬 방식
- 2차원 배열에 각 노드가 연결된 형태를 기록하는 방식
- 연결이 되어 있지 않은 노드끼리는 무한의 비용으로 작성한다.
```C
INF = 99999999

graph = [
  [0, 7, 5]
  [7, 0, INF]
  [5, INF, 0]
]
```
### 인접 리스트 방식
- 모든 노드에 대한 정보를 차례대로 연결하여 저장한다.
```C
graph = [[] for _ in range(3)]

# 각 노드에 연결된 노드 정보 저장 (노드, 거리)
graph[0].append((1, 7))
graph[0].append((2, 5))

graph[1].append((0, 7))

graph[2].append((0, 5))
```

###  차이점
- 행렬방식은 모든 관계를 저장하므로(연결되어 있지 않아도 수를 저장함) 메모리가 불필요하게 낭비된다.
- 리스트 방식은 연결된 정보만 저장하기 때문에 메모리를 효율적으로 사용한다.
- 리스트 방식은 위의 이유로 특정한 두 노드가 연결되어 있는지에 대한 정보를 얻는 속도가 느리다. 연결된 데이터를 하나하나 확인해야 하기 때문

DFS
-----
- 깊이 우선 탐색
- 스택으로 구현하고, 재귀함수를 사용한다

BFS
-----
- 너비 우선 탐색
- 큐로 구현하고, 큐 자료구조를 이용한다.
