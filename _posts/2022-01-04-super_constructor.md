---
title:  "부모 생성자 호출(super(...))"
excerpt: "부모 생성자 호출에 대한 설명"
categories: Java
tags:
  - [Blog,Java]

toc: true
toc_sticky: true
 
date: 2022-01-24
last_modified_at: 2022-01-24
---

<img width="753" alt="1" src="https://user-images.githubusercontent.com/95912146/150686359-37b99a17-7d62-4ef4-9978-540876d8647d.png">
<img width="749" alt="2" src="https://user-images.githubusercontent.com/95912146/150686361-1e0da6b4-0c45-409e-9d13-866873fe62e7.png">


## **실습코딩내용**

```java

package p02.superclass_constructor;
// 부모 클래스

// class를 만들 때 만약 부모 class 역할을 한다면, 기본적으로 default constructor를 만들어 놓아야만 함.
public class Parent {
	int homePhoneNumber;
	
	public Parent() {
		System.out.println("Parent - default constructor 호출");
	}

	public Parent(int homePhoneNumber) {
		this.homePhoneNumber = homePhoneNumber;
		System.out.println("Parent - Parent(int homePhoneNumber) 호출");
	}
}

```

```java

package p02.superclass_constructor;

// 자식클래스
public class Child extends Parent {
	
	public Child() {
		System.out.println("Child - default constructor 호출");
	}

	public Child(int homePhoneNumber) {
		System.out.println("Child - Child(int homePhoneNumber) 호출");
		this.homePhoneNumber = homePhoneNumber;
	}
}


````


```java

package p02.superclass_constructor;

// 1. 자식 class를 new로 인스턴스 생성할 때 기본적으로 부모 default constructor 먼저 실행하고, 그 이후에 자식 constructor 수행
public class ConstructorEx {

	public static void main(String[] args) {
		Child c1 = new Child();
		
		Child c2 = new Child(10);
	}

}


````


```java

콘솔 출력 내용 :
Parent - default constructor 호출
Child - default constructor 호출
Parent - default constructor 호출
Child - Child(int homePhoneNumber) 호출


```