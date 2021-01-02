문제. 1
-----
- 전자 매장에 부품이 N 개 있다. 각 부품은 정수 형태의 고유한 번호가 있다.
- 손님이 M 개 종류의 부품을 대량으로 구매하려고 한다.
- 이때 가게 안에 부품이 모두 있는지 확인하는 프로그램을 작성하시오.

### 입력 조건
- 첫째 줄에 정수 N 이 주어진다 (1 <= N <= 1,000,000)
- 둘째 줄에는 공백으로 구분하여 N 개의 정수가 주어진다. 정수는 1 ~ 1,000,000 이다
- 셋째 줄에 정수 M 이 주어진다 (1 <= N <= 100,000)
- 넷째 줄에는 공백으로 구분하여 M 개의 정수가 주어진다. 정수는 1 ~ 10억 이다

### 출력 조건
- 첫째 줄에 공백으로 구분하여 각 부품이 존재하면 YES, 없으면 NO 를 출력한다.

코드. 1
-----
### 이진 탐색
- 이진 탐색 알고리즘을 사용하여 해결한다.
```C
def binary_search(array, target, start, end):
  while start <= end:
    mid = (start + end) // 2
    if array[mid] == target:
      return mid
    elif array[mid] > target:
      end = mid - 1
    else:
      start = mid + 1
  return None
  
n = int(input())
array = list(map(int, input().split()))
array.sort
m = int(input())
x = list(map(int, input().split()))

for i in x:
  result = binary_search(array, i, 0, n - 1)
  if result != None:
    print('Yes', end = ' ')
  else:
    print('No', end = ' ')
```
### 계수 정렬

### SET 함수 사용

문제. 2
------
- 절단기에 높이 H 를 지정하면 줄지어서 한번에 잘라준다. 높이가 H 보다 긴 부분은 H 위의 부분이 잘릴 것이고, 낮은 떡은 잘리지 않는다.
### 입력 조건
- 첫째 줄에 떡의 개수 N 과 요청한 떡의 길이 M 이 주어진다. (1 <= N <= 1,000,000)(1 <= M <= 2,000,000,000)
- 둘째 줄에는 떡의 개별 높이가 주어진다. 떡 높이의 총합은 항상 M 이상이므로 손님은 필요한 양 만큼 떡을 사갈 수 있다.
- 높이는 10억 보다 작거나 같은 양의 정수 또는 0 이다.
### 출력 조건
- 적어도  M 만큼의 떡을 가져가기 위해 절단기에 설정할 수 있는 높이의 최대값을 출력한다.

해결. 2 
-----
- 이진 탐색 문제이면서 파라메트릭 서치 유형의 문제다.
- 파라메트릭 서치는 최적화 문제를 결정 문제로 바꾸어 해결하는 기법이다.   
원하는 조건을 만족하는 가장 알맞은 값을 찾는 문제에 주로 사용한다.
- 적절한 높이를 찾을 떄까지 절단기의 높이를 반복해서 조정하면 된다.
- 이 높이면 적절한가? 예, 아니오를 반복해서 탐색 범위를 좁혀나가는 문제다.

코드. 2
-----
```C
n, m = map(int, input().split())
array = list(map(int, input().split()))

start = 0
end = max(array)

result = 0
while start <= end:
  total = 0
  mid = (start + end) // 2
  for x in array:
    total = x - mid
  if total < m:
    end = mid - 1
  else:
    result = mid
    start = mid + 1
    
print(result)
```
