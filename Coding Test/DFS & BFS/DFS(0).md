 문제
 -----
- N X M 크기의 얼음 틀이 있다. 구멍이 뚫린 부분은 '0', 칸막이가 존재하는 부분은 '1' 로 표시한다.
- 구멍이 뚫려 있는 부분끼리 상, 하, 좌, 우로 서로 연결되어 있는 것으로 본다.
- 이때 얼음 틀의 모양이 주어졌을 때 생성되는 총 아이스크림 개수를 구하는 프로그램을 작성하시오.
### 입력 조건
- 첫 번째 줄에 얼음 틀의 세로 길이 N 과 가로 길이 M 이 주어진다.
- 두 번째 줄부터 N + 1 번째 줄까지 얼음 틀의 형태가 주어진다.
- 구멍이 뚫린 부분은 '0', 그렇지 않은 부분은 '1' 이다.
### 출력 조건
- 한 번에 만들 수 있는 아이스크림의 개수를 출력한다.

해결 
-----
- DFS 로 해결할 수 있다.

코드 
-----
```C
n, m = map(int, input().split())

graph = []
for i in range(n):
  graph.append(list(map(int, input().split())))

def dps(x, y):
  if x <= -1 or x >= n or y <= -1 y >= m:
    return False
  if graph[x][y] == 0:
    graph[x][y] = 1
    dps(x - 1, y)
    dps(x + 1 , y)
    dps(x, y - 1)
    dps(x, y + 1)
    return True
  return False
  
result = 0
for i in range(n):
  for j int range(m):
    if dps(i, j) == True:
      result += 1
      
print(result)
```

출처 
-----
 
