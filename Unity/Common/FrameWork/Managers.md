Managers
-----
- 매니저들을 관리하는 스크립트
- 싱글턴으로 사용하고, 모든 스크립트에서 접근이 가능하게 한다.
- 기본적으로 매니저들은 MonoBehavior를 상속하지 않고 있고, Managers에서만 상속을 한다.
- Managers는 각 매니저들의 인스턴스를 가지고 있고, 초기화를 진행 한다.
- MonoBehavior은 Managers만 상속하므로 매 프레임마다 검사하는 코드가 있으면 Managers에서 관리한다.

Input Manager
-----
- 입력을 담당하는 매니저.
- Action을 이용하여 입력을 받았을 때 이벤트를 뿌려준다.
- 매 프레임 마다 검사를 해야하므로 Managers의 Update문에서 검사한다.

Sound Manager
-----
- 소리를 담당하는 매니져.
- Sound를 넣는 빈 오브젝트를 생성하고, 그 안에 AudioSources를 생성한다.
- AudioClip을 Load할 때 Dictionary로 저장하여 두번째 재생부터는 저장된 곳에서 꺼내서 사용한다.

Resources Manager
-----
- Resources를 관리하는 매니저
- 경로를 받아서 Load를 해준다.
- Instantiate를 매핑해서 오브젝트를 생성한다.

출처
-----
- Inflearn 강좌
