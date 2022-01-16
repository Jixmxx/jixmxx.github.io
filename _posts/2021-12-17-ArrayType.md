---
title:  "Array 타입"
excerpt: "Array에 대한 설명"
categories: Java
tags:
  - [Blog, Java, Array]

toc: true
toc_sticky: true
 
date: 2022-01-16
last_modified_at: 2022-01-16
---
<img width="751" alt="1" src="https://user-images.githubusercontent.com/95912146/149653355-1b58f6a0-d5ab-4384-b1ac-58b816fa3c88.png">
<img width="751" alt="2" src="https://user-images.githubusercontent.com/95912146/149653356-e8ac25e8-1983-407f-9590-62c6cee37e7f.png">
<img width="749" alt="3" src="https://user-images.githubusercontent.com/95912146/149653357-66764970-ccad-4559-84fa-75c5c5dbf96d.png">
<img width="749" alt="4" src="https://user-images.githubusercontent.com/95912146/149653358-3ce22f3c-26f5-467e-a867-9ef0a2b0ed71.png">
<img width="749" alt="5" src="https://user-images.githubusercontent.com/95912146/149653359-bdd7ee62-a750-4fae-a116-7ff49c53ba8e.png">
<img width="751" alt="6" src="https://user-images.githubusercontent.com/95912146/149653360-2c073dc2-a18a-4a15-a9cf-70e49784454e.png">
<img width="750" alt="7" src="https://user-images.githubusercontent.com/95912146/149653361-c1616ade-a529-45bb-a48c-ce8d490d8f87.png">
<img width="751" alt="8" src="https://user-images.githubusercontent.com/95912146/149653363-ab51cff8-639c-4358-82bb-85540b4b7a14.png">
<img width="748" alt="9" src="https://user-images.githubusercontent.com/95912146/149653364-33b9d8f9-93bf-43e3-9f2a-3cc4cccdb524.png">
<img width="748" alt="10" src="https://user-images.githubusercontent.com/95912146/149653366-0517803e-6a95-4473-b418-1cfddc76c407.png">
<img width="751" alt="11" src="https://user-images.githubusercontent.com/95912146/149653368-af0717ad-736f-4ebe-bf9c-285cb6130013.png">
<img width="749" alt="12" src="https://user-images.githubusercontent.com/95912146/149653369-42f1ca3f-dc56-46a2-8ed2-aee4d5a59254.png">
<img width="751" alt="13" src="https://user-images.githubusercontent.com/95912146/149653370-2c5a20d3-e576-45d3-9235-87e342109ae5.png">
<img width="749" alt="14" src="https://user-images.githubusercontent.com/95912146/149653371-a2f32452-941e-4a88-995f-c4fd87f7fba4.png">
<img width="745" alt="15" src="https://user-images.githubusercontent.com/95912146/149653373-894dfc1e-f21f-4898-aab8-7c504e8861e2.png">
<img width="746" alt="16" src="https://user-images.githubusercontent.com/95912146/149653374-ed5a7ee8-415e-4737-ae4b-da149fb274c7.png">
<img width="746" alt="17" src="https://user-images.githubusercontent.com/95912146/149653375-654f314d-4b0f-4626-ab34-757837c47e85.png">
<img width="751" alt="18" src="https://user-images.githubusercontent.com/95912146/149653376-e4cfa084-e72a-441c-95ab-48fdf0bd5b84.png">
<img width="749" alt="19" src="https://user-images.githubusercontent.com/95912146/149653378-1dbe7dfe-dd74-42e3-adb2-8255c5bc4c58.png">
<img width="747" alt="20" src="https://user-images.githubusercontent.com/95912146/149653379-28f0b6fd-53fe-4e19-a0c0-9f9dcbbc907c.png">
<img width="745" alt="21" src="https://user-images.githubusercontent.com/95912146/149653380-442d4ff1-798b-4b78-9672-2ce1306851de.png">
<img width="747" alt="22" src="https://user-images.githubusercontent.com/95912146/149653382-7a3c2077-904d-4d80-a951-ad8e1f4bc011.png">
<img width="746" alt="23" src="https://user-images.githubusercontent.com/95912146/149653383-245c7bce-b95b-4724-837c-3aa003dcde50.png">
<img width="740" alt="24" src="https://user-images.githubusercontent.com/95912146/149653384-15a1fbb4-cbc5-4b60-af13-4cd8adf08923.png">
<img width="748" alt="25" src="https://user-images.githubusercontent.com/95912146/149653386-faf7a94a-8833-46fc-b7b4-ed97ceb56fc0.png">
<img width="741" alt="26" src="https://user-images.githubusercontent.com/95912146/149653387-007ff343-f5f6-4603-a49a-df6e337d125b.png">
<img width="733" alt="27" src="https://user-images.githubusercontent.com/95912146/149653388-f163dc7d-199b-4803-a647-3b9b9967ecc5.png">
## **실습코딩내용**
<br>

### Array
```java

package p03.array.basic;

// 1. 배열(Array) 선언 문법
//	1) 배열원소type +[] + 변수이름
//		=> 예를 들면, int[] arr로 선언을 하면 배열의 변수이름은 arr이고, 배열원소의 type은 int 라는 의미
//	2) 배열타입 + 변수이름으로 구성되어 있는데 배열타입은 배열원소 type+[]
//		=> 예를 들면, int[] arr로 선언을 하면 배열타입은 int[]임
//	3) 배열 원소 변수의 값을 읽거나 수정할 때 항상 배열이름,[index] 방식으로 사용함(단, 배열 첫번째 원소의 index는 0임)
//	4) 배열 전체 원소의 갯수를 구할 때는 변수이름.length를 사용하면됨
// 2. 배열 원소에 값을 집어 넣는 방법
//	1) 배열 변수를 선언하면서 초기값을 넣는방법
//		- {}를 사용, 예를 들면 {10, 20 , 30, 40, 50}는 5개의 원소를 가지면서 배열 원소들의 초기값은 10, 20, 30, 40, 50을 갖는 배열 생성 
//	2) 배열변수만 선언하고 배열원소 갯수 및 원소값은 나중에 넣는 방법
//  3) 배열 전체 원소 갯수(배열크기)는 선언하지만 배열원소의 값은 없는 배열만 생성
//		-일반적으로 이방법을 제일 많이 사용
//		-int[4] 의미 : 원소 type이 int인 원소 4개를 갖는 배열
public class ArrayEx {

	public static void main(String[] args) {
		// 1. 초기값을 이용하여 배열원소 값 설정
		int[] arr = { 10, 20, 30, 40, 50 };

//		arr[0] = 5;
		System.out.println("arr의 첫번째 원소 = " + arr[0]);
		System.out.println("arr의 2번째 원소 = " + arr[1]);
		System.out.println("arr의 3번째 원소 = " + arr[2]);
		System.out.println("arr의 4번째 원소 = " + arr[3]);
		System.out.println("arr 배열 전체 원소 갯수 = " + arr.length);

		// int arr1[]으로 배열 선언 가능한데, 비추천(old fashion, C language가 처음 사용했던 방식)
		int arr1[] = { 50, 60, 70, 80 };
		System.out.println("arr1의 첫번째 원소 = " + arr1[0]);
		System.out.println("arr1의 2번째 원소 = " + arr1[1]);
		System.out.println("arr1의 2번째 원소 = " + arr1[2]);
		System.out.println("arr1의 3번째 원소 = " + arr1[3]);
		System.out.println("arr1 배열 전체 원소 갯수 = " + arr1.length);

		double[] arr2 = { 1.0, 2, 3, 4 };
		System.out.println("arr2의 첫번째 원소 = " + arr2[0]);
		System.out.println("arr2의 2번째 원소 = " + arr2[1]);
		System.out.println("arr2의 2번째 원소 = " + arr2[2]);
		System.out.println("arr2의 3번째 원소 = " + arr2[3]);
		System.out.println("arr2 배열 전체 원소 갯수 = " + arr2.length);

		// 2. 배열변수만 선언하고 배열원소 갯수 및 원소값은 나중에 넣는 방법
		int[] arr3;
		// new를 사용할 때는 항상 new + data type으로 사용(예 : new string, new Scanner, new int[])
		arr3 = new int[] { 5, 6, 7, 8 };
		System.out.println("arr3의 첫번째 원소 = " + arr3[0]);
		System.out.println("arr3의 2번째 원소 = " + arr3[1]);
		System.out.println("arr3의 2번째 원소 = " + arr3[2]);
		System.out.println("arr3의 3번째 원소 = " + arr3[3]);
		System.out.println("arr3 배열 전체 원소 갯수 = " + arr3.length);

		// 3. 배열 전체 원소 갯수(배열크기)는 선언하지만 배열원소의 값은 없는 배열만 생성
		//		-일반적으로 이방법을 제일 많이 사용
		//		-int[4] 의미 : 원소 type이 int인 원소 4개를 갖는 배열
		int[] arr4 = new int[4];
		arr4[0] = 10;
		arr4[1] = 20;
		arr4[2] = 30;
		arr4[3] = 40;
		System.out.println("arr4의 첫번째 원소 = " + arr4[0]);
		System.out.println("arr4의 2번째 원소 = " + arr4[1]);
		System.out.println("arr4의 2번째 원소 = " + arr4[2]);
		System.out.println("arr4의 3번째 원소 = " + arr4[3]);
		System.out.println("arr4 배열 전체 원소 갯수 = " + arr4.length);
	}
}


```
<br>
<br>

```java

package p03.array.basic;

// Array에서 for문 사용 (while, do~while에서도 사용 가능)
public class ArrayEx2 {

	public static void main(String[] args) {
		int[] arr = { 10, 20, 30, 40, 50, 60 };
		double[] arr2 = { 1.0, 2.0, 3.0, 4.0 };

		for (int i = 0; i < arr.length; i++) {
			System.out.println("arr[" + i + "] = " + arr[i]);
		}
		for (int i = 0; i < arr2.length; i++) {
			System.out.println("arr2[" + i + "] = " + arr2[i]);
		}
		// 향상된 for문 (improved for : Java 1.6부터 사용가능한 새로운 for문)
		// javascript, python등 다른 언어에서 제공하는 for문 기능과 유사하게 만든 새로운 for문
		// 기계어로 compole이 되면 전통적인 for문 문법으로 변환함
		for (int element : arr) {
			System.out.println(element);
		}
		for (double element : arr2) {
			System.out.println(element);
		}
	}
}


```
<br>
<br>

```java

package p03.array.basic;

import java.util.Scanner;

// 배열을 사용한 코딩 단순화(simplifying coding) 예제
// 1. 어떤 결과값을 구하기 위해 배열을 사용하여 코딩 단순화 가능
//		- 예를 들면, 달력의 월 데이터를 입력받아 해당 월 정보를 출력할 경우에는 String[]의 months라는 배열을 선언하여
//		- months 변수의 index값을 이용
public class ArrayEx8 {

   public static void main(String[] args) {
      String[] months = {"1월", "2월", "3월", "4월", "5월", "6월", "7월", "8월", "9월", "10월", "11월", "12월"};

      Scanner input = new Scanner(System.in);
      
      System.out.println("달력 숫자를 입력하세요 (1 ~ 12 사이 숫자)");
      int monthNumber = input.nextInt();
      
      System.out.println("이번 달은" + months[monthNumber-1] + "입니다.");
      
//      switch(monthNumber) {
//      case 1:
//         System.out.println("이번 달은 1월 입니다.");
//         break;
//      case 2:
//         System.out.println("이번 달은 2월 입니다.");
//         break;
//      case 3:
//         System.out.println("이번 달은 3월 입니다.");
//         break;
//      case 4:
//         System.out.println("이번 달은 4월 입니다.");
//         break;
//      case 5:
//         System.out.println("이번 달은 5월 입니다.");
//         break;
//      case 6:
//         System.out.println("이번 달은 6월 입니다.");
//         break;
//      case 7:
//         System.out.println("이번 달은 7월 입니다.");
//         break;
//      case 8:
//         System.out.println("이번 달은 8월 입니다.");
//         break;
//      case 9:
//         System.out.println("이번 달은 9월 입니다.");
//         break;
//      case 10:
//         System.out.println("이번 달은 10월 입니다.");
//         break;
//      case 11:
//         System.out.println("이번 달은 11월 입니다.");
//         break;
//      case 12:
//         System.out.println("이번 달은 12월 입니다.");
//         break;
      }
   }

```
<br>
<br>

```java

package p03.array.call_by_reference;
// call by value
//	method parameter가 primitive type인 경우를 말함. 즉 method parameter로 실제값이 전달
//	- method의 결과값을 전달하려면 return 명령어를 사용해야함
// call by reference
//	- method parameter가 참조 type인 경우를 말함. 즉 method parameter로 힙메모리의 주소가 전달
//	- method의 결과값을 전달하려면 return 명령어를 사용해도 되고, parameter로 참조타입을 전달해도 됨 
public class CallByReferenceEx {

	public static void main(String[] args) {
		int x = 1;
		int[] y = new int[10];

		for (int i = 0; i < y.length; i++) {
			y[i] = 0;
		}

		passArrayParameter(x, y);

		System.out.println("x = " + x);
		System.out.println("y[0] = " + y[0]);
	}

	public static void passArrayParameter(int number, int[] numbers) {
		number = 1001;
		numbers[0] = 3333;
	}
}

```
<br>
<br>

```java

package p04.two_dim_array;

// 2차원 배열(2 Dimensional Array)
// 1. Table 형태의 데이터를 관리하기 위해서 사용
// 2. 2차원 배열은 1차원 배열에서 원소가 1차원이 배열로 생각할 수도 있음
//		- personGroup[1]의 원소는 primitive type이 아닌 1차원 배열
//		  => personGroup[1]의 원소는 -> {"2", "김의실", "경남", "공무원"}
//		  => 1차원 배열 {"2", "김의실", "경남", "공무원"}가 힙메모리에 추가로 생성되기 때문에
//			 personGroup[1]에는 1차원 배열의 주소값을 가짐
//			 그래서 1차원 배열인 onePerson변수에는 1차원 배열의 주소값을 가짐
// 3. personGroup[1][2]
//		- 2차원 배열인 personGroup의 2번째 행(행번호1)의 3번째 열(열번호2)인 "경남" 데이터값을 가리킴
//		- 행 : row, row index값은 0부터 시작
//		- 열 : column, column index값은 0부터 시작
//		- personGroup 2차원 배열을 행렬로 표현하면 3행 X 4열 구조를 가짐
public class TwoDimArrayEx {

   public static void main(String[] args) {
      String[][] personGroup = {
            {"1", "박철호", "서울", "회사원"},
            {"2", "김의실", "경남", "공무원"},
            {"3", "오수철", "경기", "연예인"}
      };
      // personGroup 1차원 배열의 각 주소 출력
      System.out.println("personGroup[0] 주소 = " + System.identityHashCode(personGroup[0]));
      System.out.println("personGroup[0] 주소 = " + System.identityHashCode(personGroup[1]));
      System.out.println("personGroup[0] 주소 = " + System.identityHashCode(personGroup[2]));
      
      // personGroup[1] => 원소타입이 String인 1차원 배열
      String[] onePerson = personGroup[1];
      for (int i=0; i<onePerson.length; i++) {
         System.out.println("onePerson[" + i + "] = " + onePerson[i]);
      }
      
      System.out.println("personGroup[0][0] = " + personGroup[0][0]);
      System.out.println("personGroup[0][1] = " + personGroup[0][1]);
      System.out.println("personGroup[0][2] = " + personGroup[0][2]);
      System.out.println("personGroup[0][3] = " + personGroup[0][3]);

      System.out.println("personGroup[1][0] = " + personGroup[1][0]);
      System.out.println("personGroup[1][1] = " + personGroup[1][1]);
      System.out.println("personGroup[1][2] = " + personGroup[1][2]);
      System.out.println("personGroup[1][3] = " + personGroup[1][3]);
      
      System.out.println("personGroup[2][0] = " + personGroup[2][0]);      
      System.out.println("personGroup[2][1] = " + personGroup[2][1]);
      System.out.println("personGroup[2][2] = " + personGroup[2][2]);
      System.out.println("personGroup[2][3] = " + personGroup[2][3]);
   }

}

```
<br>
<br>

```java

package p04.two_dim_array;

// 2차원 배열 선언 방법
public class TwoDimArrayEx2 {

   public static void main(String[] args) {
      int[][] numbers = new int[4][3];
      
      numbers[0][0] = 1;
      numbers[0][1] = 2;
      numbers[0][2] = 3;

      numbers[1][0] = 4;
      numbers[1][1] = 5;
      numbers[1][2] = 6;

      numbers[2][0] = 7;
      numbers[2][1] = 8;
      numbers[2][2] = 9;

      numbers[3][0] = 10;
      numbers[3][1] = 11;
      numbers[3][2] = 12;
      
      // 행의 길이 구하기
      System.out.println("행의 길이 = " + numbers.length);
      
      // 열의 길이 구하기
      System.out.println("1번째 행의 열의 길이 = " + numbers[0].length);
      System.out.println("2번째 행의 열의 길이 = " + numbers[1].length);
      System.out.println("3번째 행의 열의 길이 = " + numbers[2].length);
      System.out.println("3번째 행의 열의 길이 = " + numbers[3].length);
      
      for (int i=0; i<numbers.length; i++) {
         for (int j=0; j<numbers[i].length; j++) {
            System.out.print(numbers[i][j] + " ");
         }
         System.out.println();
      }
   }

}



```
