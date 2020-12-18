정규좌표 (NDC : Normalized Device Coordinate)
-----
- 1을 기준으로 하는 2차원 좌표
### 정규화 (Normalization)
- 어떤 값을 1을 기준으로 하여 상대적으로 표시하는 행위.
- 정규화를 거치면서 모든 정점 좌표는 1보다 작은 값으로 바뀐다.
- 우상단 좌표 (1,1), 좌하단 좌표 (-1, -1)

화면 좌표 (SCS : Screen Coordinate System)
-----
- 화소단위를 좌표로 표시, 해상도 1024 x 768 인 화면이면, x 값은 0~1023, y 값은 0~767 사이의 값으로 분포됨.

손가락으로 표현하는 좌표계
-----
- 엄지, 검지, 중지를 직각으로 편다.
- 엄지를 x 축에, 검지를 y 축에 놓으면 중지가 z 축을 가리키게 된다.
- 왼손과 오른손으로 표현할 수 있는데, 이 둘의 차이점은 한 축의 방향이 다르다는 것이다.
### Unity 엔진은 Y-up 왼손 좌표계이다.
- 3D 프로그램들은 주로 +Y, +Z를 '위'로 선택한다.
- 각각을 위로 정한 좌표계를 Y-up, Z-up 좌표계라고 한다. (X-up인 경우는 거의 없다.)
  - 아래는 프로그램들의 좌표계 사용 기준이다.
  ```C
  DirectX의 공식 예제들은 Y-up 왼손 좌표계입니다.(차츰 오른손으로 전환중입니다.)
  OpenGL의 공식 예제들은 Y-up 오른손 좌표계입니다.
  3ds max는 Z-up 오른손 좌표계입니다.
  Blender는 Z-up 오른손 좌표계입니다.
  언리얼 엔진은 Z-up 왼손 좌표계입니다.
  유니티 엔진은 Y-up 왼손 좌표계입니다.
  ```
유니티의 좌표계
-----
### World Point
- 실제 gameObject의 transform.position 값.
### Viewport Point
- 카메라 내에서 오브젝트가 위치하고 있는 비율 (0~1 사이의 값.
### Screen Point
- 카메라 내에서 오브젝트의 위치를 해상도를 기준으로 좌표를 매긴 값.
  - 1920 x 1080 해상도라면 (0,0) 부터 (1920, 1080)까지 표현할 수 있다.
### World Point x View Point = Screen Point
- Veiw Point를 활용하여 object 가 화면 내에 없을 때 어디에 위치해 있는지 알 수 있다.
  - x < 0 화면 왼쪽 ...

출처
-----
- 정규좌표 : [huiyu's blog](https://huiyu.tistory.com/entry/컴퓨터-그래픽스-이론-정리-정규좌표와-화면좌표?category=476980)
- 왼손, 오른손 좌표계 : [게임 프로그래밍 - 오른손 좌표계, 왼손 좌표계(Handedness) + 오일러 각(Euler Angle)|작성자 HARUBY](https://https://blog.naver.com/haruby511/2215377144503D)
- 유니티의 좌표계 : [콜라한캔 Tstory](https://onecoke.tistory.com/entry/%EC%9C%A0%EB%8B%88%ED%8B%B0-%EC%A2%8C%ED%91%9C%EA%B3%84)
