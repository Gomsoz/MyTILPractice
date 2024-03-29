우선순위 큐 (Priority Queue)
=====
+ 큐와 거의 상관이 없다.
+ 큐는 FIFO 방식이지만, 우선순위 큐는 순서와 상관없이 우선순위에 따라서 데이터를 추출한다.
+ 데이터가 많을 경우 이동과 우선순위의 비교하는 데 있어서, 배열과 연결리스트는 성능이 많이 떨어진다.   
그렇기 때문에 힙을 사용한다.

힙 (Heap)
=====
### 힙은 완전 이진 트리이다.
+ 모든 노드에 저장된 우선순위는 자식 노드에 저장된 값보다 크거나 같아야 한다.   
루트노드에 저장된 데이터가 가장 커야 한다.
### 힙의 종류
+ Max Heap : 부모 노드 우선순위 >= 자식 노드 우선순위
+ Min Heap : 부모 노드 우선순위 <= 자식 노드 우선순위

힙의 구현
-----
### 구현 방법
+ 연결리스트로 힙을 구현하면 새로운 노드를 힙의 마지막에 추가하는 것이 어렵기 때문에   
배열을 일반적으로 사용한다.
+ 배열은 순차적으로 데이터를 저장하기 때문에, 마지막 노드에 접근하기가 쉽다.
+ 특정 위치의 노드 번호는 변하지 않는다.
+ 구현을 편하게 하기위해 idx 0번을 비워둔다.
    + ### 힙의 저장
        + 새로운 데이터를 마지막 위치 __(노드를 추가해도 완전 이진트리가 유지되는 위치)__ 에 저장하고,   
        부모노드와 우선순위를 비교하여 위치를 찾을 때까지 비교, 이동을 반복한다.
    + ### 힙의 삭제 
        + __루트 노드의 우선순위가 가장 높기때문에 루트 노드가 삭제된다__
        + 루트 노드를 삭제하고 마지막 노드를 루트 노드 위치로 옮긴 후에, 우선순위를 비교하면서 내려온다.   
        왼쪽노드와 오른쪽노드의 우선순위를 비교하면서 내려와야 한다.
### 배열 기반 힙의 부모, 자식 노드 얻는 법
+ 왼쪽 자식 노드 : 부모 노드의 인덱스 * 2
+ 오른쪽 자식 노드 : 부모 노드의 인덱스 * 2 + 1
+ 부모 노드 : 자식 노드의 인덱스 / 
  + ### 자식 노드가 존재하지 않은 경우
    + __왼쪽 자식 노드의 인덱스 값 > 데이터 저장 수__
    + 8번째 배열에서 데이터가 없을 경우를 생각해 보면,   
    데이터의 수는 7개이고, 부모 노드(4)에서 왼쪽 자식 노드 인덱스를 구하면 8이 나오기 때문에   
    위의 식이 성립함을 볼 수 있다.
  + ### 자식 노드가 왼쪽 노드에만 존재하는 경우
    + __왼쪽 자식 노드의 인덱스 값 == 데이터 저장 수__
    + 12번째 인덱스까지 데이터가 저장되 있다고 하면,   
    데이터의 수는 12개이고, 부모 노드(6)에서 왼쪽 자식 노드의 인덱스 값을 구하면 12가 나오기 때문에   
    위의 식이 성립함을 볼 수 있다.
### 실제 구현과의 차이점
+ 위에서 언급한 힙의 저장과 삭제의 정의와 실제 구현의 차이는   
배열의 값을 바꾸는 것이 아닌, 인덱스 값만 비교하여 자리를 찾아가야 한다.
### 우선 순위는 함수포인터를 사용하여 특정한다.
```C
typedef struct __heap
{
  PriorityComp* Comp; 우선순위를 판단하는 포인터 함수를 보관한다.
  int numOfData;
  HData heapArr[HEAP_LEN]; Heap_LEN은 define으로 정의
} Heap;
```
