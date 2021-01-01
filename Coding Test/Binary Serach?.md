이진 탐색
-----

### 재귀 함수로 구현
```C
def binary_search(array, target, start, end):
  if start > end:
    return None
  mid = (start + end) // 2
  if array[mid] == target:
    retunr mid
  elif array[mid] > target:
    return binary_search(array, target, start, mid -1)
  else:
    return binary_search(array, target, mid + 1, end)
    
n, target = list(map(int, input().split()))
array = list(map(int, input().split()))

result = bianry_search(array, target, 0, n - 1)
if result == None:
  print("원소가 존재하지 않음")
else:
  print(result + 1)
```

### 반복문을 이용하여 구현
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
  
n, target = list(map(int, input().split()))
array = list(map(int, input().split()))

result = binary_search(array, target, 0, n - 1)
if result == None:
  print("원소가 존재하지 않음")
else:
  print(result + 1)
```

코딩 테스트에서의 이진 탐색
-----
- 이진 탐색을 아무것도 없는 상태에서 구현하려면 상당히 어려울 수 있다. 그러므로 연습을 통해 익숙해져야한다.
- 다른 알고리즘에서도 폭 넓게 적용되는 원리와 유사하기 때문에 매우 중요함.
- 탐색 범위가 2000만이 넘어간다면 이진 탐색으로 문제에 접근해보길 권한다.

빠르게 입력받기
-----
- 이진 탐색 문제는 입력 데이터가 많거나, 탐색 범위가 매우 넓은 편이다.
- 그렇기 때문에 단순히 input() 을 사용하면 동작속도가 매우 느려져 시간초과로 오답 판정을 받을 수 있다.
- sys 라이브러리의 readline() 함수를 사용하면 이 문제를 해결할 수 있다.
```C
import sys
input_data = sys.stdin.readline().rstrip()

print(input_data)
```
- sys 라이브러리를 사용할 때에는 한 줄 입력받고 나서 rstrip() 함수를 꼭 호출해야 한다.
- readline() 으로 입력하면 입력 후 엔터가 줄 바꿈 기호로 입력이 되는데, 이 공백을 제거하기 위해 rstrip() 을 호출한다.
- 코드가 짧으니, 관용적으로 외우는 것이 좋다.
