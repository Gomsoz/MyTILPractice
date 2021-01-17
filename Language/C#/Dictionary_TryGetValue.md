Dictionary 의 값을 가져오기.
-----
- 일반적으로 Dictionary 의 값을 가져올 때 변수를 선언하여 값을 저장한다.
### Dictionary.TryGetValue(key, out) 사용
- TryGetValue 를 사용하면, key 값이 유효한지 확인한 후에 반환한다.
```C
dic.TryGetValue("A", out string outString);
System.Consol.WriteLine(outString);
```
- 위 코드와 같이 사용할 수 있어서, 별도의 변수를 선언하지 않아도 된다.
