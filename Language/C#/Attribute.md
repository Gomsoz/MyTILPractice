Attribute
-----
- 어셈블리, 클래스, 필드, 메소드, 프로퍼티 등과 같은 프로그래밍 요소에 부가적인 속성 정보를 추가하기 위해 사용된다.
- 이러한 정보들은 클래스안에 메타데이터 형석으로 저장되어, 어셈블리를 참조하는 여러 컴파일러에 의해 다양한 용도로 사용할 수 있다.
### [attribute attributename("positional_parameter", named_parameter = value,...)]
- __positional_parameter__ : 필수적으로 입력되어져야 하며, 생성자 매개변수에 해당한다.
- __named_parameter__ : 선택적인 입력이며, 매개변수의 이름과 값을 나타낸다.

표준 attribute
-----
### Conditional attribute
- 조건부 메소드를 작성할 때 사용한다. 일종의 조건부 컴파일 같은 역할을 한다.
- 클래스나 구조체 안에 있는 메소드에서만 사용할 수 있다.
- System.Diagnostics 네임스페이스를 포함해야 한다.
```C
#define CSHARP
using System;
using System.Diagnostics;
class ConditionalAttributeTestApp
{
  [Conditional("CSHARP")]
  public static void CsharpMethod() { Console.WriteLine("Csharp Method"); }
  [Conditional("JAVA")]
  public static void JavaMethod() { Console.WriteLine("Java Method"); }
  
  public static void Main()
  {
    ConditionalAttributeTestApp.CsharpMethod();
    ConditionalAttributeTestApp.JavaMethod();
  }
}

// 출력 : Csharp Method
```
### Obsolete Attribute
- 사용되지 않을 메소드를 표시하기 위해 사용한다.
```C
using System;
class ObsoleteAttributeTestApp
{
  [Obsolete("Old Method"]
  public static void OldMethod() { Console.WriteLine("Old Method"); }
  public static void NormalMethod() { Console.WriteLine("Normal Method"); }
  
  public static void Main()
  {
    ConditionalAttributeTestApp.OldMethod();
    ConditionalAttributeTestApp.NormalMethod();
  }
}

// 출력 : Old Method 사용에 대한 경고문구가 나온다.
// Old Method
// Normal Method
```

### DllImport
- 보통 C, C++에서 작성한 라이브러리 파일(dll)을 가져와서 사용할 때 사용된다.
```C
using System;
using System.Runtime.InteropServices; 

class Test 
{
// User32.dll 파일안의 MessageBox 함수를 불러와서 사용하는 예이다. DllImport Attribute를 이용하여
// 사용할 코드가 포함되어 있는 DLL을 넘겨주고 extern 키워드를 통해 사용하려고 하는 메소드가 외부에 있음을 알린다.
// 이렇게 하면 닷넷 환경 밖에서 개발된 코드들(C,C++ 등등)도 C#안에서 쓸 수 있다.

[DllImport("User32.Dll")]
public static extern int MessageBox(int h, string m, string c, int type);

static void Main()
{ 
  MessageBox(0, "Hello!", "In C#", 0); 
}
}
```
출처
----
- C# 프로그래밍 입문 .생능출판
- [이종철의 블로그 blog](https://blog.naver.com/leejongcheol2018/221449852570)
- [명월 일지 tistory](https://nowonbun.tistory.com/128)
