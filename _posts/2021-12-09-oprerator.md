---
title:  "연산자와 연산식"
excerpt: "연산자와 연산식, 연산의 방향과 우선순위"
categories: Java
tags:
  - [Blog, operator, expression]

toc: true
toc_sticky: true
 
date: 2021-12-28
last_modified_at: 2021-12-28
---

![연산자와연산식1](https://user-images.githubusercontent.com/95912146/147517222-8701b877-4ef8-407c-978a-5054dbb35ef0.png)
![연산자와연산식2](https://user-images.githubusercontent.com/95912146/147517226-45b4a0ee-aeb5-492b-a0c2-af87fd84545e.png)
![연산의방향과우선순위1](https://user-images.githubusercontent.com/95912146/147517236-d863cbab-f5e4-4904-a113-48e92a4a6f53.png)
![연산의방향과우선순위2](https://user-images.githubusercontent.com/95912146/147517237-5a1084f3-dd73-417f-bda5-e42905ac8f40.png)

## **실습코딩내용**
```java
// Operator precedence : 연산자 우선 순위
// 1. '=' 다음에 오는 수식에서 CPU는 왼쪽에서 오른쪽으로 연산 수행 (CPU는 1번에 최대 2개의 피연산자(operand)에 대해 연산 수행 가능)
//	  a = 5 - 2 + 3 - 6 => 
//    1) 5 - 2 부터 연산 수행 => 3
//    2) 3 + 3 => 6 
//    3) 6 - 6 = 0,
//    4) a = 0
// 2. 왼쪽에서 오른쪽으로 연산을 하되, 연산 우선순위가 높은 연산을 먼저 수행함
//    2-1) *, /, % 연산자(operator)는 +, - 연산자보다 우선 순위 높음
//    2-2) () 가 모든 연산자 보다 우선순위가 최상위임 ==> 실제로 회사에서는 ()를 적극 사용 권장
//    예)  3 - 4/2 + 8*4 - (5+2)%3
//        1) 4/2 연산 수행 => 2
//		  2) 3-2  => 1
//		  3) 1 + 8*4에서 8*4 연산 수행 => 32
//		  4) 1 + 32 => 33
//		  5) 33 - (5+2)%3 에서 (5+2) 연산 수행 => 7
//		  6) 33 - 7%3 에서 7%3 연산 수행 => 1
//		  7) 33 - 1 => 32
//	CPU가 3.3 GHz => 3.3*10^9 회수/1초

public class OperatorPrecedenceEx {

	public static void main(String[] args) {
		int expense = 0;
		
		expense = 5 - 2 + 3 - 6;
	      System.out.println("expense = " + expense);

	      expense = 3 - 4/2 + 8*4 - (5+2)%3;
	      System.out.println("expense = " + expense);

	      expense = 3 - (4/2) + (8*4) - ((5+2)%3);
	      System.out.println("expense = " + expense);

	}

}
```