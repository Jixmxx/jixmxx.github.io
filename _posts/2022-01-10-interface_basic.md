---
title:  "인터페이스의 역할과 선언"
excerpt: "인터페이스의 역할과 선언에 대한 설명"
categories: Java
tags:
  - [Blog,Java]

toc: true
toc_sticky: true
 
date: 2022-01-26
last_modified_at: 2022-01-26
---

<img width="751" alt="1" src="https://user-images.githubusercontent.com/95912146/151013834-a6fc4d04-5c51-408f-9b98-dd5799fd4ea5.png">
<img width="750" alt="2" src="https://user-images.githubusercontent.com/95912146/151013843-14ce95da-0d3e-4e8e-adc3-6861257a1a78.png">
<img width="750" alt="3" src="https://user-images.githubusercontent.com/95912146/151013844-165db90b-7483-498d-a1e3-61e465b9afdf.png">
<img width="752" alt="4" src="https://user-images.githubusercontent.com/95912146/151013846-4fc45e17-97d8-4e99-b2be-293d9f0a4e6f.png">
<img width="748" alt="5" src="https://user-images.githubusercontent.com/95912146/151013850-070d58ff-b1f8-4b2c-b24d-4ef52cbba9b2.png">
<img width="751" alt="6" src="https://user-images.githubusercontent.com/95912146/151013852-6066f1c8-02d8-42b3-be4e-71b72326bed3.png">
<img width="752" alt="7" src="https://user-images.githubusercontent.com/95912146/151013855-031e3f6a-7be0-4730-b461-7207bf6e3c68.png">

## **실습코딩내용**

```java

package p01.basic;
// 인터페이스
// 필드상수나 추상메소드 모두 public으로 선언됨(private, default, protected 사용 안함)
public interface RemoteControl {
	// public static final int MAX_VOLUME = 10;
	// public static final이 생략되어도 compile할 때 자동으로 붙여줌
	int MAX_VOLUME = 10;		// 상수
	public int MIN_VOLUME = 0;	// 상수
	
	// abstract method(추상 메소드) : public만 존재
	public abstract void turnOff();
	void turnOn();		// public abstract가 생략된 표현
	public void setVolume(int volume);	// abstract가 생략된 표현
}

```

```java

package p01.basic;

// class이름(자식) implements interface이름(부모)
// - Audio class는 RemoteControl Interface의 자식 class처럼 생각하고 프로그래밍해도 됨
public class Audio implements RemoteControl {
   private int volume;

   @Override
   public void turnOff() {
      System.out.println("Audio를 켭니다.");
   }

   @Override
   public void turnOn() {
      System.out.println("Audion를 끕니다.");
   }

   @Override
   public void setVolume(int volume) {
      if (volume > RemoteControl.MAX_VOLUME) {
         this.volume = RemoteControl.MAX_VOLUME;
      } else if (volume <= RemoteControl.MIN_VOLUME) {
         this.volume = RemoteControl.MIN_VOLUME;
      } else {
         this.volume = volume;
      }
      System.out.println("현재 Audio 볼륨 : " + this.volume);
   }
}

```

```java

package p01.basic;

// class이름(자식) implements interface이름(부모)
// - Audio class는 RemoteControl Interface의 자식 class처럼 생각하고 프로그래밍해도 됨
public class Television implements RemoteControl {
   private int volume;

   @Override
   public void turnOff() {
      System.out.println("Television를 켭니다.");
   }

   @Override
   public void turnOn() {
      System.out.println("Television를 끕니다.");
   }

   @Override
   public void setVolume(int volume) {
      if (volume > RemoteControl.MAX_VOLUME) {
         this.volume = RemoteControl.MAX_VOLUME;
      } else if (volume <= RemoteControl.MIN_VOLUME) {
         this.volume = RemoteControl.MIN_VOLUME;
      } else {
         this.volume = volume;
      }
      System.out.println("현재 Television 볼륨 : " + this.volume);
   }
}

```

```java

package p01.basic;
// 실행 클래스
// Interface 정의
// 1. 상수 필드와 추상메소드들만 사용하는 것이 원칙
//		- 2016년 Java1.8에서 default method와 static method를 추가 사용 가능하도록 확장됨
// 2. polymorphism 사용이 기본
// 3.class가 interface 사용 방법
//		- class이름 implements interface이름
//		- implements 다음에 여러개의 interface가 올 수 있음
public class RemoteControlEx {

	public static void main(String[] args) {
//		RemoteControl rc;
//		
//		RemoteControl rc = new Television();
		RemoteControl rc = new Audio();		// promotion 부모클래스(인터페이스) 변수 = 자식클래스(Interface구현클래스)
		
		rc.turnOn();		// polymorphism = 자동형변환 + 자식클래스의 override method 실행
		rc.setVolume(7);
		rc.turnOff();
		
	}
}

```