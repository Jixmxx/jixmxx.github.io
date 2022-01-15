---
title:  "Null과 NullPointerException"
excerpt: "Null과 NullPointerException란 무엇인가"
categories: Java
tags:
  - [Blog,Java]

toc: true
toc_sticky: true
 
date: 2022-01-15
last_modified_at: 2022-01-15
---

<h3>Null(널)</h3>
<ul>
<li>변수가 참조하는 객체가 없을 경우 초기값으로 사용 가능</li>
<li>참조 타입의 변수에만 저장가능</li>
<li>null로 초기화된 참조 변수는 스택 영역 생성</li>
</ul>
 ![image](https://user-images.githubusercontent.com/95912146/149614704-7a018e42-af2b-4c18-b949-f891ba167ae3.png)
<li>==, != 연산 가능</li>
![image](https://user-images.githubusercontent.com/95912146/149614932-bd4460af-2296-4b18-81a9-147fcbb1689f.png)

<h3>NullPointerException의 의미</h3>
<ul>
<li>예외(Exception) - 사용자의 잘못된 조작 이나 잘못된 코딩으로 인해 발생하는 프로그램 오류</li>
<li>NullPointerException - 참조 변수가 null 값을 가지고 있을 때<br>
-객체의 필드나 메소드를 사용하려고 했을 때 발생
</li>
</ul>
![image](https://user-images.githubusercontent.com/95912146/149615232-ca1bae7b-3e2f-4b45-8003-86b5cfe810be.png)
![image](https://user-images.githubusercontent.com/95912146/149615238-3f72510a-22d5-4298-8d4c-3b2f858a90ea.png)

