Setting the parent of a transform which resides in a Prefab Asset is disabled to prevent data corruption
-----
### 원인
- 프리펩을 불러와서 인스턴스화 하지 않고 parent(부모)를 수정할 경우 발생하는 오류
### 해결
- 불러온 프리펩을 인스턴스화 시켜준다.
```C
// PrefabUtility.InstantiatePrefab 를 사용하기 위함
using UnityEditor

GameObject newBlock = _blockImages[UnityEngine.Random.Range(0, _blockImages.Length)].gameObject;
GameObject instance = PrefabUtility.InstantiatePrefab(newBlock) as GameObject;
instance.transform.parent = blockZip;
```
