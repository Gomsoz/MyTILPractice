Unity Attributes
=====

AddComponentMenu
-----
- Addcomponent 메뉴에 지정된 스크립트를 추가 해준다.
```C
...
[AddComponentMenu("Custom Menu/Custom Script")]
public class CustomScript : MonoBehavior
{
  ...
}
...
```

ContextMenu / ContextMenuItem
----
- 컴포넌트에서 해당 함수를 임의로 실행하고 싶을 때 사용한다.
- 셋업을 하는 메소드들을 제작해두고 사용하는데 유용, 디버깅용/상황 재현용으로 사용한다.
- ContextMenu : 컴포넌트 옆의 톱니바퀴를 눌렀을 때 나타나는 메뉴.
  - ContextMenu["Menu Name"] : string 으로 메뉴를 생성한다.
- ContextMenuItem : 컴포넌트에 추가되어 있는 멤버 변수를 마우스 오른쪽 버튼을 누르면 나타나는 메뉴.
  - ContextMenuItem["Menu Name", "Function"]

```c
...
ContextMenu["Do Something"]
void DoSomething()
{
  ...
}

ContextMenuItem["String Reset", "Reset"]
public string test = string.empty;
void Reset()
{
  test = string.empty;
}
...
```





출처
-----
- [구름고래의 이스터에그](https://m.blog.naver.com/PostView.naver?isHttpsRedirect=true&blogId=kch8246&logNo=220699888329)
- [오르카의 아틀리에](https://orcacode.tistory.com/entry/Unity-MonoBehaviour%EC%97%90%EC%84%9C-%EC%9C%A0%EC%9A%A9%ED%95%98%EA%B2%8C-%EC%93%B0%EB%8A%94-Attribute-%EC%A0%95%EB%A6%AC)
- [..](https://loadofprogrammer.tistory.com/137)
