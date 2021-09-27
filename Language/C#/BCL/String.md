String
=====
- 문자열 처리와 관련된 타입들

Class
=====
System.String
System.StringBuilder
System.Text.Encoding
System.Text.RegularExpressions.Regex

System.String
-----
- 대부분의 문자열 처리와 관련되어 있다.

### Method
- 기본적으로 StringComparison 인자를 넘겨주지 않을 경우 대/소문자 비교를 수행하지만,
- StringComparison.OrdinalIgnoreCase 와 같은 인자를 넘겨주게 될 경우 대/소문자 비교를 무시할 수 있다.

- bool Contains(char value);
- bool Contains(string value);
  - 지정된 문자가 있는지 비교
  - bool Contains(char value, StringComparison comparisonType);
  - bool Contains(string value, StringComparison comparisonType);
    - 대/소문자 비교 설정

- bool EndsWith(char value);
- bool EndsWith(string value);
  - 지정된 문자가 있는지 비교
  - bool EndsWith(char value, StringComparison comparisonType);
  - bool EndsWith(string value, StringComparison comparisonType);
    - 대/소문자 비교 설정

- bool StartsWith(char value);
- bool StartsWith(string value);
  - 지정된 문자가 있는지 비교
  - bool StartsWith(char value, StringComparison comparisonType);
  - bool StartsWith(string value, StringComparison comparisonType);
    - 대/소문자 비교 설정

System.StringBuilder
-----
- string 의 변환들은 새로운 메모리 할당을 야기시킨다.
- 예를 들어 문자열을 더할 때 기존의 메모리에서 더하는 것이 아니라 새로운 메모리를 할당하고 복사하여 더하기 때문에 성능이 저하된다.
- 그러므로 문자열을 더하는 등의 작업이 많을 경우 메모리를 미리 할당하는 StringBuilder 를 사용하는 것이 좋다.

```C
string test = "Test";

// StringBuilder 객체 생성
StringBuilder sb = new StringBuilder();
sb.Append(test);
sb.Append(" !");

string newTest = sb.ToString();
```


System.Text.Encoding
-----
- 내부적으로 문자는 숫자에 대응되는데 이처럼 문자가 숫자로 표현되는 것을 인코딩이라 한다.
- 서로 같은 인코딩 타입으로 대응해야 호환이 된다.
- BCL 에서 인코딩 타입을 제공해준다. 
  - ASCII : 7비트 아스키
  - Default : 시스템 기본
  - Unicode : 유니코드 UTF-16
  - UTF32
  - UTF8


System.Text.RegularExpressions.Regex
-----
- 정규 표현식을 다루는 클래스
- 정규 표현식(RegularExpressions)
  - 문자열 처리에 대한 일반적인 규칙을 표현하는 형식의 언어

### Constructor
- public Regex (string pattern);
  - 지정된 정규식에 대해 인스턴스를 초기화한다.
```C
string email = "abc@abc.com";
Regex regex = new Regex(@"^([0-9a-z-A-Z]+)@([0-9a-zA-Z]+)(\.[0-9a-zA-Z]+){1,}");
// regex 에 등록된 패턴과 일치하는지 확인
bool isMatch = regex.IsMatch(email);
```
- public Regex (string pattern, System.Text.RegularExpressions.RegexOptions options);
  - 패턴을 수정할 수 있는 옵션을 사용하여 지정된 정규식에 대해 초기화한다.
```C
string txt = "Hello, World";

// RegexOptions.IgnoreCase 는 대소문자를 구분하지 않는 옵션이다.
Regex regex = new Regex("world", RegexOptions.IgnoreCase);

// Regex 에 등록한 수정 옵션에 따라 world 단어를 찾아서 델리게이트 함수가 반환하는 패턴으로 교체한다
string result = regex.Replace(txt, MatchFunc)
// 결과 : Hello, Replace

static string MatchFunc(Match match)
{
  return "Replace";
}
```
