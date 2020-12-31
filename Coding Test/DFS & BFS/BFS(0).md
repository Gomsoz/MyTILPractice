문제
-----
- N X M 크기의 직사각형 형태의 미로가 있다.
-시작 위치는 (1, 1)이고, 출구는 (N, M)이다.
- 괴물이 있는 부분은 '0' 이고, 없는 부분은 '1' 이다.
- 미로는 반드시 탈출할 수 있고, 괴물을 피해서 탈출해야 한다.
- 시작칸과 마지막칸을 포함하여 탈출하기 위해 움직이는 최소 거리를 구하는 프로그램을 작성하시오.
### 입력 조건
- 첫째 줄에 두 정수가 주어진다.
- 다음 N 개의 줄에는 각각 M 개의 정수('0' 과 '1')로 미로의 정보가 주어진다.

### 출력 조건
- 첫째 줄에 최소 이동 칸의 개수를 출력한다.

해설
-----
- BFS 를 이용하면 효과적이다

코드 
-----
```C
from collections import deque

n, m = map(int, input().split())

graph = []
for i in range(n):
  graph.append(list(map(int, input())))

# 상, 하, 좌, 우
dx = [-1, 1, 0, 0]
dy = [0, 0, -1, 1]

def bfs(x, y):
  # deque 사용 -> popleft()를 이용하여 큐 처럼 사용할 수 있다.
  queue = deque
  queue.append((x,y))
  # queue 가 있으면 반복한다
  while queue:
    x, y = queue.popleft()
    # 큐에서 꺼내어 4방향으로 갈 수 있는지 확인한다.
    for i in range(4):
    nx = x + dx[i]
    ny = y + dy[i]
    # 맵 밖으로 나가는 경우, 괴물(벽)을 만난 경우 되돌아간다.
    if nx < 0 or ny < 0 or nx >= n or ny >= m:
      continue
    if graph[nx][ny] == 0:
      continue
    # 한번도 가보지 않은 곳이라면 이전 큐 값에 + 1 해준다
    if graph[nx][ny] == 1:
      graph[nx][ny] = graph[x][y] + 1
      # + 1 한 값을 다시 큐에 넣어서 탐색이 끝날 때 까지 반복한다.
      queue.append(nx, ny)
    
  return graph[n - 1][m - 1]  
  
# 출력
print(def(0,0))
      
```
