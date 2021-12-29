---
title:  "메모리 사용 영역과 참조변수의 ==, != 연산"
excerpt: "메모리 사용 영역과 참조변수의 ==,!= 연산에 대한 설명"
categories: Java
tags:
  - [Blog,primitve_type,reference_type]

toc: true
toc_sticky: true
 
date: 2021-12-29
last_modified_at: 2021-12-29
---

![메모리사용영역1](https://user-images.githubusercontent.com/95912146/147615556-fa4cf34c-9511-45be-9106-7164ca135eeb.png)
![메모리사용영역2](https://user-images.githubusercontent.com/95912146/147615557-97e9eff6-6d17-4039-8253-c7e814cc8357.png)
![메모리사용영역3](https://user-images.githubusercontent.com/95912146/147615558-d4809995-e761-45a1-b7a1-fd32d305a335.png)
![메모리사용영역4](https://user-images.githubusercontent.com/95912146/147615559-e83b867c-685b-4f88-ab93-5eafb2012442.png)
![메모리사용영역5](https://user-images.githubusercontent.com/95912146/147615560-f17f8db0-7cfb-40d5-a9b8-c2584be8dac5.png)
![메모리사용영역6](https://user-images.githubusercontent.com/95912146/147615561-58e90c43-cbe0-4313-8a50-1a7bdc4ed288.png)
![메모리사용영역7](https://user-images.githubusercontent.com/95912146/147615563-60ed1bce-a8c4-415d-abba-1b9587ff3340.png)
![참조변수의==,!=연산](https://user-images.githubusercontent.com/95912146/147615564-d3553e0f-9710-4193-ad0c-80d0e3e0c743.png)

## **실습코딩내용**

```java

package p01.string_ex;

// 1. primitive data type의 특징
//	  - primitive data type 종류 : byte, short, int, ...
//	  - 메모리 방의 크기가 고정적임
// 2. 참조 타입(reference data type)의 특징
//	  - 종류 : String, 배열(array), class, interface 등
//	  - 메모리 방의 크기가 가변적임
// 3. 프로그래밍 할 때 기본데이터 타입 변수와 참조타입 변수를 메모리에 저장하는 방법
//	  1) 기본타입인 integer type a 변수에 대하여 메모리의 stack영역에 저장
//	  2) 참조타입인 String type message, message 변수에 대하여 메모리의 stack 영역에 저장
//	 *3) 기본타입 변수인 a에 대해서는 stack영역에 실제 데이터 값이 존재함
//	 *4) 참조타입 변수인 message, message2에 대해서는 메모리의 stack영역에 잡힌 8bytes에는 실제 데이터가 위치한 메모리 주소값을 가지고 있음
//		 - 참조타입 변수인 message의 실제 데이터인 "안녕하세요, 자바씨~~"는 메모리 힙 영역에 존재
// 4. 결론
//	  1) *기본타입*으로 선언된 변수는 메모리의 스택영역에 저장되고, *변수의 값도 (데이터)도 스택에 함께 저장이 됨*, *데이터 저장크키는 고정적!*
//    2) *참조타입*으로 선언된 변수는 메모리의 스택영역에 저장되나, *변수의 값은 힙에 저장*되고, *스텍에 있는 참조타입 변수에 있는 값*은
//		 힙에 저장된 데이터가 위치한 *주소*를 갖고 있음
// 5. String 참조타입 type 사용 예
//	  - 고객이름, 주소, 직업, 직장명, 상품명, 전화번호 등...
public class StringEx {

   public static void main(String[] args) {
      String message = "안녕하세요, 자바씨~~";		// message : 참조데이터 타입 변수
      String message2 = "예, 반갑습니다. 자바씨.";	
      int a = 10;								// a : 기본데이터 타입 변수
      System.out.println(message);
      System.out.println(message2);

   }

}


```

```java

package p01.string_ex;

// '==' 의미
// 1. 기본타입과 참조타입의 공통사항
// -스택메모리의 변수에 들어가 있는 데이터 값이 같은지를 check하는 것
//	. 기본타입 : 스텍메모리의 변수에 들어가 있는 데이터 값이 실제 데이터 값을 비교	
//	. 참조타입 : 스텍메모리의 변수에 들어가 있는 데이터 값이 실제 데이터가 있는 힙메모리의 주소를 비교
// 2. String의 변수의 literal값이 동일한 경우는 힙메모리에 1개만 생성함
//	  예를 들면, str1, str2 변수의 리터럴 데이터가 모두 "신민철" 인 경우 힙메모리에 "신민철 데이터만 생성되고
//			   str1과 str2 변수에 들어가 있는 힙메모리 주소는 동일함
public class StringEx2 {

   public static void main(String[] args) {
      int x = 5;
      int y = 6;
      int z = 5;
      
      if (x == y) {
         System.out.println("2개의 숫자의 값이 같다");
      } else {
         System.out.println("2개의 숫자의 값이 다르다");
      }

      if (x == z) {
         System.out.println("2개의 숫자의 값이 같다");
      } else {
         System.out.println("2개의 숫자의 값이 다르다");
      }

      String str1 = "신민철";
      String str2 = "신민철";
      
      // equals method : str1과 str2의 힙메모리에 있는 실제 데이터가 동일한지 체크
      if (str1 == str2) {
         System.out.println("2개의 문자열의 힙메모리의 주소가 같다");
      } else {
         System.out.println("2개의 문자열의 힙메모리의 주소가 다르다");
      }
      
      
      if(str1.equals(str2)) {
    	  System.out.println("2개의 문자열의 데이터가 같다.");
      }
   }

}

```

