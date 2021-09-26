정렬 Sorting
-----
- 데이터를 특정한 기준에 따라서 순서대로 나열하는 것.

### 선택 정렬
- 파이썬에서는 두 원소의 위치를 간단하게 변경할 수 있다.
```C
array[3, 5]
array[0], array[1] = array[1], array[0] #swapping
```
이를 이용하여 선택 정렬을 간단하게 구현할 수 있다.
```C
array = [7, 5, 9, 0]

for i in range(len(array)):
  min_index = i
  for j in range(i + 1, len(array)):
    if min_index > array[j]:
      min_index = j
  array[i], array[min_index] = array[min_index], array[i]
```
- 시간 복잡도는 O(N<sup>2</sup)이다.
- 기본 정렬 라이브러리와 비교한다면 매우 비효율적이나, 특정 리스트에서 가장 작은 데이터를 찾는 일이 코딩 테스트에서 잦으므로 자주 작성해봐야 한다.

### 삽입 정렬
- 데이터가 거의 정렬 되어 있을 때 효율적이다.
```C
array = [7, 5, 9, 0]

for i in range(1, len(array)):
  for j in range(i, 0, -1):
    if array[j] < array[j - 1]:
      array[j], array[j - 1] = array[j - 1], array[j]
    else:
      break
```
- 시간 복잡도는 O(N<sup>2</sup)이나, 최선의 경우 시간 복잡도는 O(N)을 가진다.
- 보통은 비효율적이지만, 정렬의 거의 되어 있는 상태에서는 퀵 정렬보다 좋은 성능을 보인다.

### 퀵 정렬
- 정렬 알고리즘 중에 가장 많이 사용되는 알고리즘
- 파이썬의 장점을 살려서 아래와 같이 구현할 수 있다.
```C
array = [5, 7, 9, 0, 3, 1, 6, 2, 4, 8]

def quick_sort(array):
  if len(array) <= 1:
    return array
    
  pivot = array[0]
  tail = array[1:]
  
  left_side = [x for x in tail if x <= pivot]
  right_side = [x for x in tail if x > pivot]
  
  return quick_sort(left_side) + [pivot] + quick_sort(right_side)

print(quick_sort(array))
```
- 기존 퀵 정렬과는 비교 연산 횟수가 증가하여 시간면에서는 비효율적이지만 기억하기 쉽다는 장점이 있다.
- 평균 시간 복잡도는 O(NlogN)이다. 최악의 경우 O(N<sup>2</sup>)을 보인다.
- 정렬이 안되어 있을수록 높은 성능을 보인다.

### 파이썬의 정렬 라이브러리
- 파이썬은 기본 정렬 알고리즘인 sorted()함수를 제공한다.
- 병합 정렬을 기반으로 만들어져 있고 최악의 경우에도 O(NlogN)을 보장한다는 특징이 있다.
- 문제에서 별도의 요구가 없다면, 단순히 정렬을 해야하는 상황에서 기본 정렬 라이브러리를 사용한다.

### 유형
- 정렬 라이브러리로 풀 수 있는 문제   
단순히 정렬 기법을 알고 있는지 물어보는 문제로 기본 정렬 라이브러리의 사용 방법을 알고 있으면 쉽게 풀 수 있다.
- 정렬 알고리즘의 원리에 대해서 물어보는 문제   
앞서 나온 선택, 삽입, 퀵 정렬등의 원리를 알고 있어야 풀 수 있다.
- 더 빠른 정렬이 필요한 문제   
퀵 정렬 기반 알고리즘으로는 풀 수 없고, 계수 정렬등의 다른 알고리즘을 이용하거나, 기존의 알고리즘을 개선해야 풀 수 있다.


