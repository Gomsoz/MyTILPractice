변수의 수직 유효 범위
-----
### 변수가 처음 생성되고 소멸할 때 까지의 코드상에서의 수직 범위
+ 변수의 범위는 좁을수록 좋다. 범위가 넓은수록 버그 발생 가능성이 높아지고, 코드를 보기 어려워진다.
+ 함수가 길어질수록 변수의 유효범위가 넓어지는 경우가 많다. -> 함수의 길이를 되도록 짧게하자.

### try 블록의 범위는 좁을수록 좋다.
+ 가급적 예외가 발생할 지점만 감싸는 것이 좋다.
+ try문을 함수 전체로 한다던지 커지게 되면 가독성도 떨어지고, 올바르게 예외처리를 할 기회도 날아갈 수 있다.
+ try문을 길게 설정하여 의도치 않은 부분에서 예외가 던져질 경우가 생길 수 있다. 

if절 안의 코드는 딱 한 줄만
-----
+ 중괄호 안의 복잡한 코드들을 밖으로 빼내어 함수로 정의하고 호출하여 중괄호 중첩을 피할 수 있다.
+ try문도 비슷하게 try문 안의 함수들을 밖으로 빼내어 사용하면 좋다.

무분별한 임시 변수 사용
-----
+ 무분별하게 임시 변수를 사용하면 가독성이 떨어진다.
```C
string temp = Func();
return temp;
```
+ return Func(); 해도 되는 코드지만 무분별하게 temp변수를 사용했다.
+ 임시변수는 가독성을 향상시킬 수 있는 경우에만 사용하는 것이 좋다.
+ 가급적이면 'temp'라는 이름은 피하는 것이 좋다.

쿼리와 명령 분리
-----
### 쿼리: 시스템 상태의 변화를 일으키지 않고 결괏값을 반환
### 명령: 시스템 상태를 변경   
### 함수는 쿼리와 명령 둘 중 하나여야만 한다.
+ 쿼리와 명령을 동시에 가지는 함수가 있다면, 그 함수의 호출자는 쿼리를 마음 편하게 호출 할 수 없을 것이다.   

수정말고 반환하라
-----
### 수정되는 데이터는 추적에 용이해야한다.
+ 변수를 직접 수정하지 않고, 함수가 수정되는 값을 반환하도록 하면 수정된 값을 추적하기 용이해진다.
```C
int totalUsedPoints = 0;
calculateTotalUsedPoint();

void calculateTotalUsedPoint(){
    for(Integer usedPoint : pointUsedHistories)
        totalUsedPoints += usedPoint; 함수내에서 필드에 직접 값을 대입
}
```
```C
int totalUsedPoints = calculateTotalUsedPoint(); 값을 반환하여 대입

int calculateTotalUsedPoint(){
    int totalUsedPoints = 0;

    for(UsedPoint point : usedPoints)
        totalUsedPoints += point.amount();

    return totalUsedPoints;
}
```

Tell, Don't ask
-----
+ 객체의 내부상태를 ask 하지말고 tell 해야 한다.
+ 객체 내부에 직접 접근하여 값을 요청하지말고 함수를 통하여 필요한 행동을 말해야한다.
```C
function moveElevator(int floorNumber) {
    if(elevator.currentFloor == floorNumber) 객체 내부에 접근하여 값을 가져와서 비교한다.
        return;                              이경우에 객체 내부 상태가 변경되면 이부분도 변경되야 한다.

    elevator.move(floorNumber);
    elevator.currentFloor = floorNumber;
}
```
```C
class Elevator{
    private integer currentFloor;

    function move(int floorNumber){
        if(currentFloor == floorNumber)
            return;

        moveInternal()

        this.currentFloor = floorNumber
    }
}

class ElevatorManager{
    private Elevator elevator;

    function moveElevator(int floorNumber){
        elevator.move(floorNumber); 함수를 호출만 할뿐, 객체 내부에 관여하지않는다.
    }                               객체 내부가 변경되더라도 신경 쓸 필요가 없다. -> 캡슐화가 잘 되어있다.
}
```
