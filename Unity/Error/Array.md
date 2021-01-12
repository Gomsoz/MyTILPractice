IndexOutOfRangeException
-----
- IndexOutOfRangeException: Index was outside the bounds of the array
### 원인
- 배열의 인덱스 범위를 넘어가서 저장을 시도할 경우 발생.
### 해결
- 배열의 인덱스를 조정한다.
- 배열의 인덱스를 넘어가지 않도록 저장한다.

NullReferenceException
-----
- NullReferenceException: Object reference not set to an instance of an object.
### 원인
- null 예외는 다양하지만 배열에서 나오는 오류는 배열을 초기화 하지 않고 사용했을 때 발생한다.
### 해결
- 배열을 초기화 한다.

ArgumentException
------
- ArgumentException: GetComponent requires that the requested component 'GameObject' derives from MonoBehaviour or Component or is an interface.
### 원인
- 
### 해결
- GameObject 대신 Transform을 사용한다.
