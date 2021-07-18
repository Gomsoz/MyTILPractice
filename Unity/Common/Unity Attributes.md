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

ColorUsage
-----
- [ColorUsage(Alpha, hdr, minBrightness, MaxBrightness, minExposureValue, maxExposureValue)]
- 컬러픽커를 사용하게 해준다.
```C
[ColorUsage(false)]
public Color colorPicker;
```

SerializeField
-----
- [SerializeField]
- private 변수들을 인스펙터 상에 표시해준다.
```C
[SerializeField]
priavte int value = 0;
```

Serializable
-----
- [Serializable]
- 인스펙터 상에 구조체나 클래스를 표시해준다.
```C
[Serializable]
public class PlayerStats
{
  public string name;
  public int hp;
  public int mp;
}
```

NonSerialized
-----
- [NonSerialized]
- public 으로 선언된 변수들을 숨겨준다
- HideInspector 와 비슷하지만, 인스펙터에서 변수가 수정된 적이 있으면 HideInspector 는 값을 유지하지만, NonSerialized 는 인스펙터의 값을 유지하지 않고 스크립트의 초기값을 유지한다.
- 인스펙터 상에서 사용되지 않지만, 다른 스크립트에서 사용될 경우 사용할 수 있다.
```C
[Nonserialized]
public int value = 0;
```

HideInInsepector
-----
- [HideInspector]
- public 인 변수를 인스펙터 상에서 표시가 안되게 해준다.
```C
[HideInspector]
public int value = 0;
```

Header
----
- [Header(string)]
- 인스펙터 상에섯 변수들을 묶어주어 정리 해 준다.
```c
[Header("Player Stats")]
public int hp = 0;
public int mp = 0;
```

Range
-----
- [Range(min, max)]
- 인스펙터 상에서 변수 값을 변경할 때 슬러이더 방식으로 변경할 수 있게 해준다.
```c
[Range(0, 10)]
public int value = 0;
```

Space
-----
- [Space(value)]
- value 만큼 공백을 띄워준다.
```C
public int value1;

[Space(10)]
public int value2;
```

Tooltip
-----
- [Tooltip(string)]
- 툴팁을 인스펙터 상에 추가시킨다.
```C
[Tooltip("Tooltip")]
public int value = 0;
```

TextArea / Multiline
-----
- [TextArea(value)], [Multiline(min, max)]
- 1 줄의 TextField 를 여러 줄로 작성하게 해준다.
- Multiline 은 폭에 맞춰 줄바꿈이 되지 않고 스크롤이 생성되지 않는다.
- TextArea 는 줄바꿈과 스크롤이 생성된다. 특별한 이유가 없다면 TextArea 를 사용한다. 
```C
[Multiline(5)]
public string multi = "";

[TextArea(3, 10)]
public string textArea = "";
```

RequireComponent
-----
- [RequireComponent(typeof(component))]
- 특정 컴포넌트가 붙어 있어야 한다는 제약을 건다.
- 해당 컴포넌트가 없으면 붙여주고, 삭제하려고 하면 못하게 표시한다.
```C
[RequireComponent(typeof(Rigidbody2D))]
public class Scripts : Monobehavior
{
  ...
}
```

ExecuteInEditMode
-----
- [ExecuteInEditMode]
- 게임 실행 중이 아니더라도 MonoBeahvior 를 상속한 컴포넌트의 주요 함수가 호출되는 효과.
- 호출 타이밍 :
  - 게임오브젝트가 갱신될 때
  - 더블클릭으로 Scene 을 로드할 때 Awake, Start 함수 호출
  - 인스펙터에서 컴포넌트의 변수 등을 변경할 때 Update 함수 호출

```C
[ExecuteInEditMode]
public class Scripts : MonoBehavior
{
  void Awake()
  {
    ...
  }
  
  void Update()
  {
    ...
  }
}
```

DisAllowMultipleComponent
-----
- [DisAllowMultipleComponent]
- 하나의 게임 오브젝트에 같은 컴포넌트를 여러개 붙일 수 없게 해준다.
```C
[DisAllowMultipleComponent]
public class Scripts : Monobehavior
{
  ...
}
```


출처
-----
- [구름고래의 이스터에그](https://m.blog.naver.com/PostView.naver?isHttpsRedirect=true&blogId=kch8246&logNo=220699888329)
- [오르카의 아틀리에](https://orcacode.tistory.com/entry/Unity-MonoBehaviour%EC%97%90%EC%84%9C-%EC%9C%A0%EC%9A%A9%ED%95%98%EA%B2%8C-%EC%93%B0%EB%8A%94-Attribute-%EC%A0%95%EB%A6%AC)
- [..](https://loadofprogrammer.tistory.com/137)
