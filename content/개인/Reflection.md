- [[Spring]]
- [[Java]]

---
```java
clazz.getName();
clazz.getMethods();

Method m = clazz.getMethod("bark");
m.invoke(dogInstance);

// 런타임 객체 생성
Object obj = clazz.getDeclaredConstructor().newInstance();
```

Reflection: 런타임에 클래스 구조를 동적으로 들여다보고, 조작하는 것

```java
@Autowired
private DogService dogService;
```

`@`가 앞에 붙은 걸, Annotation이라고 한다.

Reflection을 이용해, Spring은 런타임에 클래스를 스캔한다.
`@Autowired`가 붙어 있으면, 객체를 ==[[주입]]==한다.

```java
List<String> list = new ArrayList<>();

// 스프링 동작 예시:
list.getClass().getName(); // "java.util.ArrayList"
```

그러나 Type Erasure는 Reflection에 의한 참조를 막는다.
그래서 종종 트릭을 사요한다.

DI가 리플렉션으로 돌아간다


