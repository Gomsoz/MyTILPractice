Destroying assets is not permitted to avoid data loss.
-----
### 원인
- 게임오브젝트가 아닌 프리펩을 삭제하려고 할 때 발생하였음.
### 해결
- 프리펩이을 저장하는 것이 아닌, Instantiate()로 게임오브젝트를 생성하여 저장 후 삭제.
```C

public tranform card; // 드래그 드롭으로 등록
m_cardList[m_cardIdx] = card; // 프리펩을 배열에 저장
Destroy(m_cardList[m_cardIdx]); // 불가능

public tranform card; // 드래그 드롭으로 등록
GameObject go = GameObject.Instantiate(card.gameObject, transform); // 게임오브젝트 생성
m_cardList[m_cardIdx] = go.transform; // 게임오브젝트를 배열에 저장
Destroy(m_cardList[m_cardIdx]); // 가능

```
