---
title:  "StringBuffer, StringBuilder 클래스"
excerpt: "StringBuffer, StringBuilder 클래스에 대한 설명"
categories: Java
tags:
  - [Blog,Java]

toc: true
toc_sticky: true
 
date: 2022-02-02
last_modified_at: 2022-02-02
---


<img width="754" alt="1" src="https://user-images.githubusercontent.com/95912146/152154230-7baec06d-f9d6-4125-8cca-a26152a0e221.png">
<img width="756" alt="2" src="https://user-images.githubusercontent.com/95912146/152154235-5f89091b-4d72-4b78-bdeb-48baa7d69776.png">

## **실습코딩내용**

```java

package p08.stringbuilder_class;

// 1. String의 최대 단점인 문자열을 합치거나 등의 연산을 하면, heap memory에 새로운 문자열이 생성되고 기존의 문자열은 계속 남아있음
// 2. String Builder는 문자열을 합치는 등의 연산을 수행 하더라도 
//    heap memory에 기존 문자열이 수정 되도록 만들어져있어 새로운 문자열이 생성되는 것이 아님
public class StringBuilderEx {

	public static void main(String[] args) {
		StringBuilder sb = new StringBuilder();

		sb.append("Java ");
		sb.append("Program study");
		System.out.println(sb);

		sb.insert(4, "2");
		System.out.println(sb);

		sb.setCharAt(4, '6');
		System.out.println(sb);

		sb.replace(6, 13, "Book");
		System.out.println(sb);

		sb.delete(4, 5);
		System.out.println(sb);

		System.out.println("총 문자수 : " + sb.length());
		System.out.println(sb.toString());
		System.out.println(sb);
	}

}


```