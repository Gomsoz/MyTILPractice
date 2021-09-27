시간
=====
- 시간과 관련된 타입들이다.

Class
=====
System.DateTime
System.TiemSpan
System.Diagnostics.Stopwatch


System.DateTime
-----
- Struct 로 정의되어 있으며, 시간과 관련된 정보를 가질 수 있다.

### Constructor
- Public DateTime(int year, int month, int day);
  - 년 월 일
- Public DateTime(int year, int month, int day, int hour, int minute, int second);
  - 년 월 일 시 분 초
- Public DateTime(int year, int month, int day, int hour, int minute, int second, int millisecond);
  - 년 월 일 시 분 초 + 밀리초
- Public DateTime(int year, int month, int day, int hour, int minute, int second, int millisecond, DateTimeKind kind);
  - 년 월 일 시 분 초 + 밀리초 + 시간 형식

### Property
#### Static
- DateTime Now
  - 현재 시간/날짜를 확인할 수 있다.

- DateTime UtcNow
  - Now 는 지역시간 (대한민국의 경우 UTC + 9) 을 반환하고 UtcNow 는 Utc 시간을 반환한다.

#### None
- int Year { get; }
- int Month { get; }
- int Day { get; }
- int Hour { get; }
- int Minute { get; }
- int Second { get; }
- int Millisecond { get; }
  - 1초 = 1000 밀리초

- int Ticks
  - 1년 1월 1일 12시 자정을 기준으로 현재까지를 100 나노초 간격으로 흐른 값
  - 1밀리초 보다 정밀도가 높다.
```C
// 함수 실행 시간을 구하는 예
DateTime before = DateTime.Now;
...
Function();
...
DateTime after = DateTime.Now;

long gap = after.Ticks - before.Ticks
```
  - 유닉스, 자바 플랫폼의 경우 DateTime 기준값이 1970년 1월 1일을 기준으로 하여 호환 시에 1970년에 해당하는 고정 밀리초 값을 빼서 시간을 구할 수 있다.

- DateTimeKind Kind { get; }
  - 인스턴스에서 나타내는 시간이 지역시간인지 Utc 시간인지 아무것도 아닌지를 나타내는 값
  - enum DateTimeKind
    - Unspecified : 정해지지 않음
    - Utc : Utc 시간
    - Local : 지역 시간

System.TiemSpan
-----
- DateTime 타입의 빼기 연산의 결괏값을 저장하는 구조체이다.

### Property
- int Days { get; }
- int Hours { get; }
- int Minutes { get; }
- int Seconds { get; }
- int Milliseconds { get; }
  - 결괏값의 세부 정보

- double TotalDays { get; }
- double TotalHours { get; }
- double TotalMinutes { get; }
- double TotalSeconds { get; }
- double TotalMilliseconds { get; }
  - 결괏값의 차이의 총 합

System.Diagnostics.Stopwatch
-----
- TimeSpan 이외에 더 정확한 시간차 계산을 위한 타입
- 실제로 코드의 특정 구간에 대한 성능을 측정할 때 자주 사용된다.

### Property
#### Static
- readonly long Frequency;
  - 타이머 빈도, 초당 흐른 틱 수
  - ElapsedTicks 에 대해 나누면 초 단위의 시간을 잴 수 있다.
    - st.ElapsedTicks / Stopwatch.Frequency

#### None
- TimeSpan Elapsed { get; }
  - 총 경과 시간
- long ElapsedTicks { get; }
  - 총 경과 틱 수
- long ElapsedMilliseconds { get; }
  - 총 경과 밀리초

