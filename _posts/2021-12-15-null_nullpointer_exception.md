---
title:  "Null과 NullPointerException"
excerpt: "Null과 NullPointerException에 대한 설명"
categories: Java
tags:
  - [Blog,Java, null]

toc: true
toc_sticky: true
 
date: 2022-01-15
last_modified_at: 2022-01-16
---

<h3>Null(널)</h3>
<ul>
<li>변수가 참조하는 객체가 없을 경우 초기값으로 사용 가능</li>
<li>참조 타입의 변수에만 저장가능</li>
<li>null로 초기화된 참조 변수는 스택 영역 생성</li>
</ul>
 ![image](https://user-images.githubusercontent.com/95912146/149614704-7a018e42-af2b-4c18-b949-f891ba167ae3.png)
<li>==, != 연산 가능</li>
![image](https://user-images.githubusercontent.com/95912146/149614932-bd4460af-2296-4b18-81a9-147fcbb1689f.png)

<h3>NullPointerException의 의미</h3>
<ul>
<li>예외(Exception) - 사용자의 잘못된 조작 이나 잘못된 코딩으로 인해 발생하는 프로그램 오류</li>
<li>NullPointerException - 참조 변수가 null 값을 가지고 있을 때<br>
-객체의 필드나 메소드를 사용하려고 했을 때 발생
</li>
</ul>
![image](https://user-images.githubusercontent.com/95912146/149615232-ca1bae7b-3e2f-4b45-8003-86b5cfe810be.png)
![image](https://user-images.githubusercontent.com/95912146/149615238-3f72510a-22d5-4298-8d4c-3b2f858a90ea.png)
## **실습코딩내용**


```java

package p05.null_ex;

// 참조 변수의 초기값으로 null 사용 예
// 1. null의 의미 : 참조타입으로 선언된 변수의 값으로, 힙메모의 주소가 없다.
//	  => 힙메모리에 해당 변수로 생성된 객체가 없다.
// 2. 참조타입인 String, 1차원배열, 2차원배열에 사용가능하고, class, interface등 모든 참조타입의 초기값으로 사용가능
public class NullEx {

   public static void main(String[] args) {
      String name = "홍길동";
      String name1 = null;
      int[] num = null;
      int[][] num2 = null;
      String[] names = null;
      int sum = 0;

      if (name1 == null) {
         name1 = "김길동";
      }
      
      System.out.println(name1);
   }

}

```


