String 과 StringBuilder 차이
=====
### String
- value 타입이 아닌 ref 타입이기 때문에 문자열을 반복해서 변경할 때마다 새로운 인스턴스가 생성되어 성능저하가 발생한다.

### StringBuilder
- 새로운 변수를 생성하지 않고, 내부 함수로 문자열을 조합할 수 있다.

String 과 StringBuilder 사용
=====
### String
- 변경해야할 문자열의 수가 적은 경우
- 검색작업이 필요할 때

###  StringBuilder
- 반복문등에서 문자열을 많이 변경해야 하는 경우 (변경 횟수가 알 수 없는 경우)
- IndexOf, StartWith 같은 검색하는 함수가 없기 때문에 String 으로 변환해서 사용해야 한다.
- StringBuilder.MaxCapacity() 함수로 용량을 할당해야 하고, 설정 용량을 초과하면 예외를 던진다.
- UTF-16 인코딩으로 문자를 저장한다.


```C
StringBuilder sb = new StringBuilder(50);

sb.append("안녕하세요");
sb.append(" 반갑습니다");
```

출처
=====
[건앤로즈](https://hongjinhyeon.tistory.com/91)
[주형 Coding Groot](https://coding-groot.tistory.com/53)
[MSDN](https://docs.microsoft.com/ko-kr/dotnet/api/system.text.stringbuilder?view=net-5.0)
