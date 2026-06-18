- [[Java-HelloWorld]]
- [[Tomcat]]: Java로 만들어진 Java Application Server

### Java의 특징
- 모든 객체는 참조(reference)로 다룬다.
- GC, Garbage Collector: delete할 필요가 없음.
	- 근데 그만큼 신경써야 성능을 올릴 수 있다.
- 메모리 저장
	- 모든 객체(object)는 heap에
	- 원시(primitive)는 stack에
- 상속 `class Dog extends Animal { }`
	- 다중 상속 불가
- 인터페이스
	- `interface Runnable { void run(); }`
	- `class Dog implements Runnable { public void run() { ... } }`
- 접근제어자 명시
- 참조: `import com.example.Dog;`(패키지)
	- `package com.example;`
- Exception: IOException은 명시해야함

[[Java 객체]]

### 다음:
- [[Spring Boot]]

---
### 재미
- `void run();` ⇔ `void run() { }`