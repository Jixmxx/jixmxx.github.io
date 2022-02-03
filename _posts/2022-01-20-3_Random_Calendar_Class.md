---
title:  "Random, Calendar 클래스"
excerpt: "Random, Calendar 클래스에 대한 설명"
categories: Java
tags:
  - [Blog,Java]

toc: true
toc_sticky: true
 
date: 2022-02-03
last_modified_at: 2022-02-03
---

<img width="754" alt="1" src="https://user-images.githubusercontent.com/95912146/152258913-d9c16f15-89f7-4188-bf86-410fa8358fe3.png">
<img width="755" alt="2" src="https://user-images.githubusercontent.com/95912146/152258918-e6690a3e-c349-4ed7-86ce-245b7d91cb16.png">


## **실습코딩내용**

```java
package p12.etc;

import java.util.Calendar;

public class CalendarEx {

	public static void main(String[] args) {
		Calendar now = Calendar.getInstance();

		int year = now.get(Calendar.YEAR);
		int month = now.get(Calendar.MONTH) + 1;
		int day = now.get(Calendar.DAY_OF_MONTH) + 1;
		int week = now.get(Calendar.DAY_OF_WEEK);
		String strWeek = null;

		switch (week) {
		case Calendar.MONDAY:
			strWeek = "월";
			break;
		case Calendar.TUESDAY:
			strWeek = "화";
			break;
		case Calendar.WEDNESDAY:
			strWeek = "수";
			break;
		case Calendar.THURSDAY:
			strWeek = "목";
			break;
		case Calendar.FRIDAY:
			strWeek = "금";
			break;
		case Calendar.SATURDAY:
			strWeek = "토";
			break;
		case Calendar.SUNDAY:
			strWeek = "일";
			break;
		}

		System.out.println(year + "년 " + month + "월 " + day + "일 " + strWeek + "요일");

		int hour = now.get(Calendar.HOUR);
		int minute = now.get(Calendar.MINUTE);
		int second = now.get(Calendar.SECOND);
		System.out.println(hour + "시 " + minute + "분 " + second + "초");

	}

}

```

```java
package p12.etc;

import java.util.Random;

// (int)(Math.random()*45) +1 => 1 ~ 45 사이에 정수값을 무작위로 발생
//   == random.nextInt(45) + 1
public class RandomEx {

	public static void main(String[] args) {
		int[] selectNumber = new int[6];
		Random random = new Random();

		System.out.println("선택 번호 : ");
		for (int i = 0; i < 6; i++) {
			selectNumber[i] = random.nextInt(45) + 1;
			System.out.print(selectNumber[i] + " ");
		}
		System.out.println();

		int[] winNumber = new int[6];
		random = new Random();

		System.out.println("당첨번호 : ");
		for (int i = 0; i < 6; i++) {
			winNumber[i] = random.nextInt(45) + 1;
			System.out.print(winNumber[i] + " ");
		}
	}

}

```