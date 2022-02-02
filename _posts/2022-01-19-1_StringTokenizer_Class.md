---
title:  "StringTokenizer 클래스"
excerpt: "StringTokenizer 클래스에 대한 설명"
categories: Java
tags:
  - [Blog,Java]

toc: true
toc_sticky: true
 
date: 2022-02-02
last_modified_at: 2022-02-02
---

<img width="755" alt="1" src="https://user-images.githubusercontent.com/95912146/152153716-12235a3d-b6fc-46b4-ae63-13866729499e.png">

## **실습코딩내용**

```java

package p07.string_tokenizer;

// &|,|- => | : or
public class StringSplitEx {

	public static void main(String[] args) {
		String text = "홍길동&이수홍,박연수,김자바-최명호";

		String[] names = text.split("&|,|-"); // '&' or ',' or '-' 라는 뜻임

		for (String name : names) {
			System.out.println(name);
		}

	}
}


```

```java

package p07.string_tokenizer;

import java.util.StringTokenizer;

// nextToken() : heap memory 있는 데이터 1개를 가져옴
// => 가져온 데이터는 heap memory에서 제거
// hasMoreElements() : 데이터가 있으면 true 없으면 false
// => boolean type임
// StringTokenizer(text,"/") 에서 '/'는 다른 문자도 가능하다
public class StringTokenizerEx {

	public static void main(String[] args) {
		String text = "홍길동/이수홍/박연수";

		StringTokenizer st = new StringTokenizer(text, "/");
		int countTokens = st.countTokens();
		for (int i = 0; i < countTokens; i++) {
			String token = st.nextToken();
			System.out.println(token);
		}

		System.out.println();

		st = new StringTokenizer(text, "/");
		while (st.hasMoreElements()) {
			String token = st.nextToken();
			System.out.println(token);
		}

	}


```