---
title:  "정규 표현식과 Pattern 클래스"
excerpt: "정규 표현식과 Pattern 클래스에 대한 설명"
categories: Java
tags:
  - [Blog,Java]

toc: true
toc_sticky: true
 
date: 2022-02-02
last_modified_at: 2022-02-02
---


<img width="755" alt="1" src="https://user-images.githubusercontent.com/95912146/152154595-c4379c1c-432f-4488-8f38-2bbf801eac6f.png">
<img width="754" alt="2" src="https://user-images.githubusercontent.com/95912146/152154599-2152b8e3-aa3b-4d31-bc86-679ff14cc784.png">

## **실습코딩내용**

```java

package p09.regular_expression;

import java.util.regex.Pattern;

// regular expression (02|010)-\\d{3,4}-\\d{4} 설명 => 다양한 데이터 중 전화 번호만을 찾는 표현식
// 1. (02|010) : 02 또는 010, () : grouping, | : or
// 2. \\ => \ 와 같은 의미(예 : \\d{3,4} = \d{3,4}) * \ 를 사용하려면 \\ 이렇게 2개 써줘야함
// 3. d{3,4} : 숫자 최소 3자리 ~ 최대 4자리
//     => d는 [0-9] 숫자만 허용, d : digit의 약어, {3,4} 개수가 최소 3개에서 최대 4개까지 허용
// 4. d{4} : 숫자 4자리만 가능

// regular expression \\w+@\\w+\\.\\w+(\\.\\w+)? 설명 => email address를 찾는 표현식
// 1. \w+ : 단어가 1개 이상
//     => w는 (A~Z,a~z,_,0~9) 중의 1개의 문자, w: word, + : 1개 이상
// 2. ? : 없거나 1개만 존재하는 경우
// 3. . : 어떤 종류의 1개의 문자를 의미(특수 문자(*,&)를 포함한 숫자,영문자 허용) <.도 문법이기 때문에 \\룰 붙여줘야함>
//     => \. : 문자열에서 .을 찾고 싶을 때 사용
public class PatternEx {

	public static void main(String[] args) {
		String regExp = "(02|010)-\\d{3,4}-\\d{4}";
		String data = "010-123-5678";

		// data 가 regExp의 문법과 일치 하냐? 묻는 것
		boolean result = Pattern.matches(regExp, data);

		if (result) {
			System.out.println("정규식과 일치합니다.");
		} else {
			System.out.println("정규식과 일치하지 않습니다.");
		}

		regExp = "\\w+@\\w+\\.\\w+(\\.\\w+)?";
		data = "angel@naver.co.kr";

		// data 가 regExp의 문법과 일치 하냐? 묻는 것
		result = Pattern.matches(regExp, data);

		if (result) {
			System.out.println("정규식과 일치합니다.");
		} else {
			System.out.println("정규식과 일치하지 않습니다.");
		}
	}

}



```