Java는 **모든 코드가 클래스 안에 있어야 합니다.** 함수나 전역변수가 클래스 밖에 존재할 수 없어요. C++처럼 `int main()` 을 파일 최상단에 그냥 쓰는 게 불가능합니다.

- a `[filename]` should be a class name

```java
public class HelloWorld {
	public static void main(String[] args) {
		System.out.println("Hello, World!");
	}
}
```

### JVM의 순서
JVM 동작 ⇒ `HelloWorld.main()` 호출 ⇒ 실행

결론: `static`이 붙은 건 인스턴스 없이도 동작한다.
왜냐하면, 
클래스는 프로세스 메모리 상에서 참조한다: Method Area에 존재
인스턴스를 생성할 때, 클래스를 참조한다.
즉, 클래스는 하나만 존재한다.
참고: 인스턴스는 Heap에 존재

`static`이 붙지 않은 경우, 인스턴스가 존재해야 한다.
- function, variable
















