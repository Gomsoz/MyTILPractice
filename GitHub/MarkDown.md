마크다운 문법
=============

헤더 (Headers)
-------------
+ 큰제목

      This is an H1
      =============
      
    큰 제목은 이렇게 사용하는군
    ==========================

+ 작은제목

      This is an H2
      -------------
      
    작은 제목은 이렇게 사용하는군
    ---------

+ 글머리
  + 1~6까지 가능

        # Header 1
        ## Header 2
        ### Header 3
        #### Header 4
        ##### Header 5
        ###### Header 6
        ####### Header 7? -> 불가능

# 글머리
## 작은 글머리
### 더 작은 글머리
#### 더 더 작은 글머리
##### 더 더 더 작은 글머리
###### 더 더 더 더 작은 글머리
      
Block Quote
------
'>' 블럭인용문자를 사용한다.

    > BlockQuote
    > >BlockQuote
  
> BlockQuote
> + 글머리도 포함 가능
> >BlockQuote
> BlockQuote
>>>> Block
>>>Block

4개 사용후에 3개 사용하니 뒷 내용이 앞 내용에 붙어서 출력됨

목록
-----
+ 숫자목록(순서가 있는 목록)
  + 순서가 있는 목록은 숫자와 점을 사용한다
  + 무조건 내림차순으로 정렬된다
  
    1. 첫번째
    2. 두번째
    3. 세번쨰
    
1. 첫번째
2. 두번째
3. 세번째

+ 기호목록(순서가 없는 목록)
  + *,+,-를 사용한다.
  + 혼합해서 사용하는 것이 가능하다.
  
        + 1
          * 2
            - 3

+ 1
  * 2
    - 3
 
코드블럭작성
------

+ 들여쓰기

  4개의 공백 또는 하나의 탭으로 들여쓰기를 만나면 변환되기 시작하여 들여쓰지 않는 행을 만날 때까지 변환이 계속된다.
  코드 블럭을 만들고 싶은 내용 앞 뒤로 enter를 해줘야 함.
  
   Normal paragraph
   
      Code block
    
   Normal paragraph
   
+ 코드블럭 코드 사용하기 (1)

  코드블럭을 만들고 싶은 내용 앞, 뒤로 "```"를 넣어준다
  
  ```
  Console.WriteLine.Printf("Hello Wrold!");
  ```
  
+ 코드블럭 코드 사용하기 (2)

  ```<pre><code>{code}</code></pre>```를 이용한다.
  
  <pre>
  <code>
  Console.WriteLine.Printf("Hello World!");
  </code>
  </pre>
  
수평선
------

  + 아래와 같이 작성하여 수평선을 만들 수 있다. 미리보기로 출력할 때 페이지 나누기 용도로 많이 사용
  
        * * *
        ***
        *****
        - - -
        --------------
    
    * * *
    ***
    *****
    - - -
    --------------
    
링크
------
  + 참조링크
  
        [link keyword][id] 한칸 띄우고 참조를 넣어준다.

        [id] : URL "Optional Title here"
        
        Link: [Google][googleLink] 한칸 띄우고 참조를 넣어준다.

        [googleLink]: https://google.com
      
      
Link: [Google][googleLink]

[googleLink]: https://google.com "Go Google"

  + 외부링크
  
        [Title](link)
        [Google](https://google.com, "google link")

[Google](https://google.com, "google link")

  + 자동연결
      
      일반적인 URL 혹은 이메일주소인 경우 적절한 형식으로 링크를 형성한다.

        * 외부링크: <http://example.com/>
        * 이메일링크: <address@example.com>
      
* 외부링크: <http://example.com/>
* 이메일링크: <address@example.com>

강조
----

    *기울이기*
    _기울이기_
    **두껍게**
    __두껍게**
    ~~취소선~~

+ *기울이기*
+ _기울이기_
+ **두껍게**
+ __두껍게**
+ ~~취소선~~

이미지
----
  +아래와 같이 사용가능함. 추후에 예시를 사용해볼 필요가 있음.

    ![Alt text](/path/to/img.jpg)
    ![Alt text](/path/to/img.jpg "Optional title")
    
줄바꿈
----

  + 3칸이상 띄어쓰기하면 줄이 바뀐다.
  
        줄바꿈   
        줄바꿈!
      
줄바꿈   
줄바꿈!



참고자료
----
+ ihoneymon님 [github](https://gist.github.com/ihoneymon/652be052a0727ad59601#this-is-a-h1)


+ 쥰님 [blog](https://blog.naver.com/jooeun0502/221956294941)

