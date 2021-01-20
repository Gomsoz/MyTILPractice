특정 인터페이스를 가지고 있는지 확인하고 함수 호출하기.
-----
```C
UnitInterface.IUnit IUnit = (UnitInterface.IUnit)_unit.GetComponent(typeof(UnitInterface.IUnit));
IUnit.GetUnitType();
```
