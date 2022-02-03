---
title:  "Array 클래스"
excerpt: "Array 클래스에 대한 설명"
categories: Java
tags:
  - [Blog,Java]

toc: true
toc_sticky: true
 
date: 2022-02-03
last_modified_at: 2022-02-03
---

<img width="756" alt="1" src="https://user-images.githubusercontent.com/95912146/152257893-fafe272b-8b76-4342-9007-f236e3b4a452.png">
<img width="755" alt="2" src="https://user-images.githubusercontent.com/95912146/152257900-c753119c-16ea-499e-8968-1aa108db8bfa.png">
<img width="755" alt="3" src="https://user-images.githubusercontent.com/95912146/152257902-4e7bc21e-beb8-4d16-89e6-9a678991eb3a.png">


## **실습코딩내용**

```java
package p10.arrays_method;

import java.util.Arrays;

public class ArrayCopyEx {

	public static void main(String[] args) {
		char[] arr1 = { 'J', 'A', 'V', 'A' };

		// 복사방법 1
		char[] arr2 = Arrays.copyOf(arr1, arr1.length);
		System.out.println(arr2);

		// 복사방법 2
		char[] arr3 = Arrays.copyOfRange(arr1, 1, 3);
		System.out.println(arr3);

		// 복사방법 1
		char[] arr4 = new char[arr1.length];
		System.arraycopy(arr1, 0, arr4, 0, arr1.length);
		System.out.println(arr4);
	}

}

```


```java
package p10.arrays_method;

public class Member implements Comparable<Member> {
	String name;

	public Member(String name) {
		this.name = name;
	}

	@Override
	public int compareTo(Member o) {

		return name.compareTo(o.name); // 오름차순 a.compareTo(b)
//		return -name.compareTo(o.name); // 내림차순 -a.compareTo(b)
//	    return o.name.compareTo(name);  // 내림차순  b.compareTo(a)
	}

}

```


```java
package p10.arrays_method;

import java.util.Arrays;

// 배열 원소 오름차순 정렬 : {99, 95, 44, 97, 98} => {44, 95, 97, 98, 99}
// Array.sort method : array 원소의 값을 기준으로 오름차순 으로 정리
// 1. parameter로 int[], String[] 등을 지정하면 해당하는 method를 실행 (method overloading)
// 2. sort method를 사용 하려면 Comparable interface를 implements한 class를 사용 해야만 함
//    - 단, int, float, double 등 primitive type은 Comparable interface를 implements할 필요 없음
// 3. a.compareTo(b)의 return값이 다음과 같이 나오게 만들면 오름차순으로 정렬(sorting)
//   1) a < b 이면, -1 return (-1을 return하면 Array.sort메소드에서 a,b 순서를 유지하도록 코딩되어 있음)
//   2) a == b 이면, 0 return (0을 return하면 Array.sort메소드에서 a,b 순서를 유지하도록 코딩되어 있음)
//   3) a > b 이면, 1 return (1을 return하면 Array.sort메소드에서 a,b 순서를 바꾸도록 코딩되어 있음)
// 3-1. String의 a.compareTo(b) method의 return값 예제 (오름차순 정렬)
//    - 알파벳, 가, 나, 다 순으로 sorting
//     1) a가 "김길동" < b가 "나한수"인 경우, -1 return
//     2) a가 "김길동" == b가 "김길동"인 경우, 0 return
//     3) a가 "나한수" < b가 "김길동"인 경우, 1 return
// 4. a.compareTo(b)의 return값이 다음과 같이 나오게 만들면 내림차순으로 정렬(sorting)
//   1) a < b 이면, 1 return (1을 return하면 Array.sort메소드에서 a,b 순서를 유지하도록 코딩되어 있음)
//   2) a == b 이면, 0 return (0을 return하면 Array.sort메소드에서 a,b 순서를 유지하도록 코딩되어 있음)
//   3) a > b 이면, -1 return (-1을 return하면 Array.sort메소드에서 a,b 순서를 바꾸도록 코딩되어 있음)
public class SortEx {

	public static void main(String[] args) {
		int[] scores = { 99, 95, 44, 97, 98 };

		for (int i = 0; i < scores.length; i++) {
			System.out.println("scores[" + i + "] = " + scores[i]);
		}
		System.out.println();

		Arrays.sort(scores);

		for (int i = 0; i < scores.length; i++) {
			System.out.println("scores[" + i + "] = " + scores[i]);
		}
		System.out.println();

		String[] names = { "홍길동", "박동수", "김민수" };
		Arrays.sort(names);

		for (int i = 0; i < names.length; i++) {
			System.out.println("names[" + i + "] = " + names[i]);
		}
		System.out.println();

		Member[] members = { new Member("홍길동"), new Member("박동수"), new Member("김민수") };
		Arrays.sort(members);

		for (int i = 0; i < members.length; i++) {
			System.out.println("members[" + i + "] = " + members[i].name);
		}

	}

}

```