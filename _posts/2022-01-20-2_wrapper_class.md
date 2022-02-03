---
title:  "Wrapper 클래스"
excerpt: "Wrapper 클래스에 대한 설명"
categories: Java
tags:
  - [Blog,Java]

toc: true
toc_sticky: true
 
date: 2022-02-03
last_modified_at: 2022-02-03
---

<img width="753" alt="1" src="https://user-images.githubusercontent.com/95912146/152258306-86724658-5faf-482b-994d-f1f477f67ce3.png">
<img width="755" alt="2" src="https://user-images.githubusercontent.com/95912146/152258309-1f5d5447-d11b-4bdb-acf7-80e4f7e3ac69.png">
<img width="754" alt="3" src="https://user-images.githubusercontent.com/95912146/152258311-70e53058-57af-494c-9ed8-56ce75927e0e.png">
<img width="754" alt="4" src="https://user-images.githubusercontent.com/95912146/152258312-ef58794c-3e9c-4e2c-a0c8-a2ba1c6cb1d6.png">
<img width="755" alt="5" src="https://user-images.githubusercontent.com/95912146/152258313-dbe9ea15-5f46-45dd-a62c-dfa31a357b96.png">


## **실습코딩내용**

```java
package p11.wrapper_class;

public class AutoBoxingUnBoxingEx {

	public static void main(String[] args) {
		Integer obj1 = 100; // auto boxing : primitive data type을 Integer로 자동 형 변환
		System.out.println(obj1.intValue());

		int i1 = obj1; // auto unboxing : Integer data type을 primitive data type으로 자동 형 변환
		System.out.println(i1);

		int result = obj1 + 100; // auto unboxing
		System.out.println(result);

		Double obj2 = 100.23; // auto boxing
		System.out.println(obj2.doubleValue());

		double d1 = obj2; // auto unboxing
		System.out.println(d1);

		double result1 = obj2 + 12.3; // auto unboxing
		System.out.println(result1);
	}

}

```


```java
package p11.wrapper_class;

public class BoxingUnBoxingEx {

	public static void main(String[] args) {
		// Boxing : primitive data type => wrapper class로 변환
//		Integer obj1 = new Integer(100);
		Integer obj1 = 100;                // 이렇게 적어도 가능
		Integer obj2 = new Integer("200");
		Integer obj3 = Integer.valueOf("300");
		
		Double obj4 = new Double(100.3);
		Double obj5 = new Double("200.45");
		Double obj6 = Double.valueOf("300.12");

		// UnBoxing : wrapper class로 변환 => primitive data type
		int i1 = obj1.intValue();
		int i2 = obj2.intValue();
		int i3 = obj3.intValue();
		
		int i4 = (int) obj1.longValue();
		long l4 = obj1.longValue();

		System.out.println(i1);
		System.out.println(i2);
		System.out.println(i3);

		double d1 = obj4.doubleValue();
		double d2 = obj5.doubleValue();
		double d3 = obj6.doubleValue();

		System.out.println(d1);
		System.out.println(d2);
		System.out.println(d3);

	}

}

```


```java
package p11.wrapper_class;

// String 문자열을 primitive data type으로 변환
public class StringToPrimitiveEx {

	public static void main(String[] args) {
		int a = Integer.parseInt("10");
		double b = Double.parseDouble("3.14");
		boolean c = Boolean.parseBoolean("true");

		System.out.println(a);
		System.out.println(b);
		System.out.println(c);
	}

}

```


```java
package p11.wrapper_class;

// 1. obj1과 obj2는 300이라는 같은 primitive value를 가졌지만 heap memory에 별로로 생성
//   즉, obj1과 obj2의 heap memory의 주소가 달라서 'obj1 == obj2'는 false가 나옴
//   (Integer는 class 명이다)
// 2. Wrapper class의 값을 비교할 경우
//   1) primitive type으로 변환하여 비교
//   2) equals() method를 사용하여 비교
public class ValueCompareEx {

	public static void main(String[] args) {
		Integer obj1 = 300;
		Integer obj2 = 300;

		System.out.println("obj1 == obj2 결과값 : " + (obj1 == obj2));
		System.out.println("obj1.intValue() == obj2.intValue() 결과값 : " + (obj1.intValue() == obj2.intValue()));
		System.out.println("obj1.equals(obj2) 결과값 : " + (obj1.equals(obj2)));

	}

}

```