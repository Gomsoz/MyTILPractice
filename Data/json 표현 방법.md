json file
----
- name/value 쌍으로 된 컬렉션 구조로 이루어 지는데, 이는 다양한 프로그래밍 언어에서 불러올 수 있다.
### Value
- "name": value,
```C
"id": "1",
"name": "string",
"rate": "80"
"enable": true,
...
```
### Array
- "arrayname":[   
{   
  ...   
}   
{   
  ...   
}   
]
```C
"array":[
{
  "id": "1",
  "name": "string",
  "rate": "80"
  "enable": true,
}
{
  "id": "2",
  "name": "string2",
  "rate": "100"
  "enable": true,
}
]
```

출처
-----
- [AI딥러닝 C# python blog](https://blog.naver.com/rhukjin/222036135558)
