Delegate
-----
- 일을 줄 때 각각 객체에 일을 직접 줄 수 있지만, delegate객체에게 일을 주면 delegate객체가 할일들을 다른 객체에 뿌려준다.
### Delegate 선언
```C
private delegate void MyDelegate(int i);
private void MyFunc(int i);

1. MyDelegate temp = new MyDelegate(MyFunc);
2. MyDelegate temp = My Func;
3. MyDelegate temp = delegate(int i) {Debug.log(i)}

1. 기본
2. 간략하게
3. 익명함수 사용
```

Call Back
-----
- A라는 메서드를 호출할 때 B라는 메서드를 매개변수로 넘겨주고, A메서드에서 B메서드를 호출 하는 것.
- 함수에서 다른 함수를 호출할 때 보고받기 위해 사용하는 방법.
- 어떤 이벤트가 발생했을 때, 새로운 동작이 필요하다면   
해당 객체에 주기적으로 물어보기 보다는 작업이 마쳤을 때 해당 시기에 콜백을 해주는 것이 더 효율적이다.

Delegate Chain
----
- 하나의 메서드 뿐 아니라 여러개의 메서드를 이어 붙일 수 있다
- +=, -= 연산자를 통해 추가, 삭제가 가능하다.

Event
-----
- 단순하게 말하면 Delegate에 event를 수식해서 선언한 것이다.
- delegate와 차이는 안정성 때문에 외부에서 직접 사용할 수 없다는 것이다.
- event는 객체의 상태 변화나 사건의 발생을 알리는 용도로 사용하고, delegate는 콜백 용도로 사용하게 된다.
- '='연산은 사용할 수 없고 '+='연산을 사용해 이벤트핸들러에 등록할 수 있다.

Action
-----


출처
-----
- [SEE REAL VALUE님 Blog](https://blog.naver.com/enter_maintanance/221639746861)
