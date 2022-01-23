---
title:  "클래스 상속"
excerpt: "클래스 상속에 대한 설명"
categories: Java
tags:
  - [Blog,Java]

toc: true
toc_sticky: true
 
date: 2022-01-24
last_modified_at: 2022-01-24
---

<img width="753" alt="1" src="https://user-images.githubusercontent.com/95912146/150686042-0223a260-c6b2-4a72-9d33-dd7b2b3cce15.png">
<img width="752" alt="2" src="https://user-images.githubusercontent.com/95912146/150686043-aca7be60-5a16-4a4b-a668-3f760c3717f2.png">

## **실습코딩내용**

```java
package p01.basic;

// 상속 기본
// 1. 부모의 field, method 모두 사용 가능 (단, 부모의 constructor는 사용 불가)
//    - 부모뿐만 아니라, 부모위의 부모(할아버지/할머니) 등의 먼 조상들 class의 field, method 모두 사용 가능
// 2. 사용문법 : 자식클래스이름 extends 부모클래스이름
// 3. Java는 부모 클래스를 선언할 때 1개만 가능
//    - C++은 부모 클래스를 여러 개 선언하여 사용 가능
// 4. 같은 부모를 가진 형제 class들 간의 필드, 메소드는 사용 불가
public class InheritanceEx {

	public static void main(String[] args) {
		Person p = new Person();
		p.name = "아담";
		
		p.speak();
		p.eat();
		p.sleep();
		p.walk();

		Student s = new Student();
		s.name = "홍길동학생";
		s.age = 23;
		
		s.study();
		s.speak();
		s.eat();
		s.sleep();
		s.walk();
		
		StudentWorker sw = new StudentWorker();
		sw.name = "김학생워커";
		sw.age = 22;
		sw.work();
		sw.study();
		sw.speak();
		sw.eat();
		sw.sleep();
		sw.walk();
		
		Researcher r = new Researcher();
		r.name = "강연구원";
//		r.study();
		r.research();
		r.speak();
		r.eat();
		r.sleep();
		r.walk();
		
		Professor pf = new Professor();
		pf.name = "홍교수";
		pf.teach();
		pf.research();
		pf.speak();
		pf.eat();
		pf.sleep();
		pf.walk();
		
	}

}


```

```java

package p01.basic;

// 상속 : 자식 생성자를 먼저 호출하기 전에 부모 생성자를 먼저 JVM이 자동 호출하여 힙메모리에 부모 인스턴스 생성하고 그 다음에 자식 인스턴스 생성함
// - 예를 들면, new StudentWorker()를 호출하면, JVM이 new Person()을 먼저 자동 실행하고, 다음으로 new Student()를 실행하고
//   마지막으로 new StudentWorker()를 실행하여, 힙메모리에 부모인 Student 인스턴스와 할아버지인 Person 인스턴스를 힙메모리에 자동 생성해줌
public class InheritanceEx2 {

	public static void main(String[] args) {
		StudentWorker sw = new StudentWorker();
		
		sw.name = "김학생워커";
		sw.age = 22;
		sw.work();
		sw.study();
		sw.speak();
		sw.eat();
		sw.sleep();
		sw.walk();
	}

}


````