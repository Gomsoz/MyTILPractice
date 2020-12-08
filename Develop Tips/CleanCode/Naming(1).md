줄여쓰지 않는다.
-----

### 일반적으로 통용되는 단축어 idx, cnt등 이외에 자신만 알아 볼 수 있도록 축약하면 안된다.
  + 이는 다른 사람이 단축어를 볼 때 의미를 파악하기위해 변수 선언부까지 올라가야되므로, 시간과 동선을 낭비시킨다.
  + 명확한 의도가 담기도록 길어야한다. 축약해서 알아보기 힘든 변수명보다 의도가 명확한 변수명이 낫다.
  
        stmt (x) statement(o)
        
모호하게 짓지 않는다.
-----

### 이름에 서술성이 부족한 경우 본래 의도를 담지 못하는 모호한 이름이 되는 경우가 있다.
  + 대표적인 예로 Process(처리하다)를 보면, 무엇을 처리하다라는 의미가 담겨있다.   
  __StringProcessor__ 라는 클래스가 있다고 할 때, 다른 사람이 보기엔 문자열을 처리하는 함수로만 생각 할 수 있다.   
  하지만 이런 이름은 클래스가 하는 일에 대해 충분한 설명이 되지 못한다.   
  __StringFormatter__ 와 같은 클래스의 역할을 구체화시켜서 이름을 지어야 코드를 여러번 보는 수고를 덜 수 있다.
  
  + List의 첫번째 요소를 반환하는 함수 __GetFirstElement__ 라는 함수가 있다고 하면,  
      ```c
        String GetFirstElemnt(List<string> list)
        {
          if(list == null || list.isEmpty())
            return "Empty";
            
          return list.get(0);
        }
      ```
  + List가 null이거나 비었을 경우에 "Empty"를 반환하지만 함수명으로만 보면 "Empty"가 List의 첫번째 요소라고 착각할 수 있다.   
  그러므로 함수이름을 지을 때 비었을 경우에 "Empty"를 반환하는 구체적인 내용을 추가하는 것이 좋다.
  
        GetFirstElement 보다
        GetFirstElementOrEmpty 가 더 구체적이며 좋은 이름이다.
        
  + 어떤 이벤트의 시작날짜와 시간을 클래스로 표현한다고 해보면,   
  __eventStartDate__ 보다 __eventStartDateAndTime__ 으로 표현하는 것이 좋다.   
  전자는 이벤트 시작 날짜만 포함한다고 착각을 일으킬 수 있으며, 후자는 날짜와 시간 둘 다 포함하는 것으로 판단할 수 있다.   
  
  + 이처럼 이름은 구체적으로 지을 때 이름으로만으로도 하는 일을 알 수 있기 때문에 함수 내부를 본다거나, 여러번 확인 할 필요가 없어진다.
  
### One word for one abstract concept
  + 한 개념당 하나의 단어를 사용하여 이름을 짓는다면 모호해지는 것을 피할 수 있다.
  
길다고 다 좋은건 아니다.
-----
### 위에서 말한 __One word for one abstract concept__ 을 지킨다면 이름이 길어지지 않을 것이다.   
  + 즉, 한 개념당 하나의 단어로만 표현한다면 쓸데없이 길어지는 경우를 피할 수 있다.
  
### 함수 이름에 파라미터나 리턴타입같은 다른 시그니처 구성 요소와 중복되는 단어가 있다면 제거하는 것도 방법이다.
  + __List<string> GetAllNonNullValuesFromMap(Map<string, string> map)__ 이란 함수에서 파라미터에 Map 타입이 있기 때문에   
  함수명에서 FromMap부분을 생략 할 수 있을 것이다.   
  ___List<string> GetAllNonNullValues(Map<string, string> map)__ 과 같이 작성하면 된다.
  
불필요한 단어 중복은 피한다.
-----
### 클래스의 이름으로부터 의미를 파악할 수 있는 내용은 이름에서 빼는 것이 좋다.
  ```c
    public class PlayerMove
    {
      public void PlayerMoveLeft(){...}
      public void PlayerMoveRight(){...}
      public void PlayerMove Up(){...}
      ...
    }
  ```
+ 위 클래스와 같이 클래스의 이름으로부터 PlayerMove라는 의미를 파악할 수 있기 때문에, 불필요하게 작성된 매서드들의 PlayerMove를 삭제하고   
Left, Right로 간편하게 만들 수 있다.

난해함을 피한다.
-----
+ 처음보는 전문용어나, 나만 알고있는 특이한 단어의 사용을 피한다.
+ 통상적으로 사용하고 있는 단어들은 사용해도 괜찮지만(board, upboard등) 사용하려는 단어가 다른 단어로 대체가 불가능 할 경우에 사용하는 것이 좋다.
