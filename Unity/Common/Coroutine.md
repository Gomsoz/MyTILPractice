Coroutine 코루틴
=====
- 실행을 중지하여 unity에 제어권을 돌려주고, 계속할 때에는 다음 프레임에서 중지한 곳부터 실행을 계속할 수 있는 기능.
- 메인 루틴을 진행하다가 StartCoroutine을 만나면 코루틴에 제어권을 넘겨준 다음 새로운 루틴을 돌리고,
yield를 만나면 루틴을 중단하고 다시 메인 루틴에 제어권을 넘겨준다.
- 이후 메인 루틴이 진행하다가 지정한 위치(unity 함수 호출 순서에 따른 yield문 호출 위치)를 만나면 중단한 위치에 돌아와서 마저 진행한다.
- 위 과정이 매우 빠른 시간안에 반복되면 마치 두개의 루틴이 돌고 있는 것처럼 보이기 때문에 멀티 쓰레드처럼 보이지만,
비동기적으로 동작하기 때문에 엄연히 말하면 멀티 쓰레드는 아니다.
- 코루틴은 update를 거의 완전히 대체할 수 있기 때문에 런타임중에 계속 돌아가야하는 것이 아니라면 update보다 코루틴을 추천한다.<sup>*1</sup>

yield문
-----
- yield return null : 다음 프레임 까지 대기
- yield return new WaitForSeconds(float) : 입력한 sec만큼 대기
- yield return new WaitFixedUpdate() : 다음 프레임의 FixedUpdate까지 대기
- yield return new WaitForEndOfFrame() : 모든 래더링 작업이 끝날 때까지 대기
- yield return StartCoroutine(string) : 입력한 다른 코루틴이 끝날 때까지 대기
- yield return new www(string) : 입력한 웹 통신 작업이 끝날 때까지 대기
- yield return new Asyncloeration : 비동기 작업이 끝날 때까지 대기
- yield break : 코루틴 종료   
...


출처
-----
- 코루틴, *1 : [감귤사전](https://blog.naver.com/cdw0424/221624274241)
