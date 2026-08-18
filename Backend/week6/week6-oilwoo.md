# Week 06 - Java / Spring Backend Role-Based Interview 1

---

## 제출 기준

- 필수 답변: ROLE-001 ~ ROLE-020
- 선택 답변: ROLE-021 ~ ROLE-040

---

## 필수 질문

## [ROLE-001] Java의 특징과 JVM 위에서 동작한다는 것의 의미를 설명해 주세요.

답변:
- 쉽게 한 줄로 설명하면, **Java는 소스 코드를 플랫폼에 독립적인 바이트코드로 컴파일하고, 각 운영체제에 맞는 JVM이 이를 실행하는 객체지향 언어**입니다.
- Java 컴파일러인 `javac`는 `.java` 소스 파일을 JVM 명령어가 담긴 `.class` 바이트코드로 변환합니다.
- JVM은 Class Loader로 클래스를 불러오고 바이트코드를 실행하며, 메모리 관리와 Garbage Collection 같은 실행 환경을 제공합니다.
- Windows와 Linux의 JVM 구현은 서로 다르지만 동일한 `.class` 파일을 이해할 수 있습니다. 따라서 해당 환경에 맞는 JVM이 있다면 같은 바이트코드를 여러 운영체제에서 실행할 수 있습니다.
- JVM은 처음에 바이트코드를 해석하고, 반복해서 실행되는 코드는 JIT Compiler가 기계어로 컴파일하여 성능을 높일 수 있습니다.
- JVM 시작, JIT Warm-up, 추가 메모리 사용에 따른 비용이 있지만 플랫폼 독립성과 자동 메모리 관리라는 장점이 있습니다. 따라서 Java 성능을 측정할 때는 초기 Warm-up 구간과 실제 측정 구간을 구분하는 것이 좋습니다.

참고 자료:
- https://www.ibm.com/docs/ko/i/7.6.0?topic=platform-java-virtual-machine
- https://www.ibm.com/docs/ko/sdk-java-technology/8?topic=reference-jit-compiler
- https://docs.oracle.com/en/java/javase/26/docs/specs/jvms/index.html

---

## [ROLE-002] JVM의 역할과 Java 코드가 실행되는 과정을 설명해 주세요.

답변:
- 쉽게 한 줄로 설명하면, **JVM은 Java 바이트코드를 불러와 실행하고 실행 중에 필요한 메모리를 관리하는 환경**입니다.
- Java 코드가 실행되는 과정은 다음과 같습니다.
  1. Java Compiler인 `javac`가 `.java` 소스 파일을 `.class` 바이트코드로 컴파일합니다.
  2. JVM이 시작되면 Class Loader가 필요한 `.class` 파일을 불러와 Loading, Linking, Initialization 과정을 수행합니다.
  3. 클래스 정보, 객체, 메서드 호출 정보 등이 Method Area, Heap, Stack 같은 Runtime Data Area에 저장됩니다.
  4. Execution Engine은 바이트코드를 Interpreter로 한 명령씩 실행하고, 반복해서 실행되는 코드는 JIT Compiler로 기계어로 컴파일하여 성능을 높입니다.
  5. Garbage Collector는 Heap에서 더 이상 참조되지 않는 객체를 찾아 메모리를 회수합니다.
- JVM은 운영체제별 차이를 대신 처리하므로 같은 바이트코드를 여러 환경에서 실행할 수 있도록 하고, Class Loading, 코드 실행, 메모리 관리와 Garbage Collection을 담당합니다.

참고 자료:
- https://www.ibm.com/docs/ko/i/7.6.0?topic=platform-java-virtual-machine
- https://docs.oracle.com/en/java/javase/26/docs/specs/jvms/jvms-2.html
- https://docs.oracle.com/en/java/javase/26/docs/specs/jvms/jvms-5.html

---

## [ROLE-003] JVM 메모리 구조인 Method Area, Heap, Stack, PC Register, Native Method Stack에 대해 설명해 주세요.

답변:
- 쉽게 한 줄로 설명하면, **Method Area와 Heap은 모든 Thread가 공유하고, Stack, PC Register, Native Method Stack은 Thread마다 별도로 생성됩니다.**
- **Method Area**는 JVM이 불러온 클래스의 구조, Field와 Method 정보, Runtime Constant Pool 등을 저장하는 논리적 영역입니다. HotSpot JVM에서는 클래스 메타데이터를 Metaspace로 구현하는 등 세부 구현은 JVM마다 다를 수 있습니다.
- **Heap**은 `new`로 생성한 객체와 배열이 저장되는 공유 영역이며, Garbage Collector가 주로 관리합니다.
- **Stack**은 Thread마다 생성되며 Method가 호출될 때마다 Frame이 쌓입니다. Frame에는 지역 변수, Operand Stack, Method 호출과 반환에 필요한 정보가 저장됩니다.
- **PC Register**는 Thread가 현재 실행 중인 JVM 명령의 위치를 나타냅니다. Thread별로 존재하므로 각 Thread가 어디까지 실행했는지 관리할 수 있습니다.
- **Native Method Stack**은 Java가 아닌 C나 C++ 등으로 구현된 Native Method를 실행할 때 사용됩니다.
- 예를 들어 `Member member = new Member();`에서 지역 변수 `member`의 참조값은 Stack에 저장되고 실제 `Member` 객체는 Heap에 저장됩니다.

참고 자료:
- https://docs.oracle.com/en/java/javase/26/docs/specs/jvms/jvms-2.html#jvms-2.5
- https://docs.oracle.com/en/java/javase/26/docs/specs/jvms/jvms-2.html#jvms-2.6
- https://www.ibm.com/docs/ko/i/7.6.0?topic=platform-java-virtual-machine

---

## [ROLE-004] Java에서 Primitive Type과 Reference Type의 차이를 설명해 주세요.

답변:
- 쉽게 한 줄로 설명하면, **Primitive Type 변수는 실제 값을 가지고, Reference Type 변수는 객체를 가리키는 참조값을 가집니다.**
- Primitive Type에는 `byte`, `short`, `int`, `long`, `float`, `double`, `char`, `boolean`의 8가지가 있으며 `null`을 가질 수 없습니다.
- Reference Type에는 Class, Interface, Array 등이 있으며 객체를 직접 저장하는 것이 아니라 객체를 가리키는 참조값을 저장하고 `null`을 가질 수 있습니다.
- Java에서 대입은 항상 변수의 값을 복사합니다. Primitive Type은 실제 값이 복사되므로 두 변수가 독립적이지만, Reference Type은 참조값이 복사되므로 두 변수가 같은 객체를 가리킬 수 있습니다.
- 예를 들어 `int b = a` 이후 `b`를 변경해도 `a`는 바뀌지 않습니다. 반면 `Member m2 = m1` 이후 `m2.name`을 변경하면 `m1`과 `m2`가 같은 객체를 가리키므로 `m1.name`에서도 변경된 값이 조회됩니다.
- Java의 Method 인자 전달도 항상 Pass-by-Value입니다. Reference Type을 전달할 때는 객체 자체가 아니라 객체를 가리키는 참조값이 복사됩니다.
- Primitive Type은 항상 Stack, Reference Type은 항상 Heap에 저장된다고 단정할 수는 없습니다. 실제 저장 위치는 지역 변수인지 객체의 Field인지와 JVM 구현에 따라 달라질 수 있습니다.

참고 자료:
- https://docs.oracle.com/javase/specs/jls/se26/html/jls-4.html#jls-4.2
- https://docs.oracle.com/javase/specs/jls/se26/html/jls-4.html#jls-4.3.1
- https://docs.oracle.com/javase/specs/jls/se26/html/jls-4.html#jls-4.12.2

---

## [ROLE-005] Java의 equals()와 ==의 차이를 설명해 주세요.

답변:
- 쉽게 한 줄로 설명하면, **`==`는 Primitive Type에서는 값을 비교하고 Reference Type에서는 같은 객체를 가리키는지 비교하며, `equals()`는 객체가 정의한 논리적 동등성을 비교합니다.**
- Primitive Type에 `==`를 사용하면 두 실제 값이 같은지 비교합니다.
- Reference Type에 `==`를 사용하면 두 참조값이 같은 객체를 가리키는지 확인합니다. 이를 실제 메모리 주소를 직접 비교한다고 표현하기보다 객체의 동일성을 비교한다고 표현하는 것이 정확합니다.
- `Object.equals()`의 기본 구현은 `==`와 같이 객체의 동일성을 비교하지만, Class에서 `equals()`를 Override하면 객체의 내용이나 식별 기준으로 동등성을 비교할 수 있습니다.
- `String`은 `equals()`를 Override하여 문자열의 내용을 비교합니다. 따라서 각각 `new String("Java")`로 생성한 두 객체에 `==`를 사용하면 `false`, `equals()`를 사용하면 `true`가 반환됩니다.
- `equals()`를 Override할 때는 `equals()`가 `true`인 두 객체가 같은 `hashCode()`를 반환하도록 함께 구현해야 HashMap이나 HashSet에서 올바르게 동작합니다.

참고 자료:
- https://docs.oracle.com/javase/specs/jls/se26/html/jls-15.html#jls-15.21
- https://docs.oracle.com/en/java/javase/26/docs/api/java.base/java/lang/Object.html#equals(java.lang.Object)
- https://docs.oracle.com/en/java/javase/26/docs/api/java.base/java/lang/String.html#equals(java.lang.Object)

---

## [ROLE-006] String, StringBuilder, StringBuffer의 차이를 설명해 주세요.

답변:
- 쉽게 한 줄로 설명하면, **`String`은 변경할 수 없는 문자열이고, `StringBuilder`와 `StringBuffer`는 내부 내용을 변경하면서 문자열을 조합할 수 있는 객체**입니다.
- **String**은 Immutable 객체이므로 생성된 문자열의 내용이 바뀌지 않습니다. 문자열을 연결하거나 변경하면 기존 객체를 수정하는 것이 아니라 결과를 나타내는 새로운 String이 만들어집니다.
- **StringBuilder**는 Mutable하며 동기화를 지원하지 않습니다. 따라서 단일 Thread에서 반복적으로 `append()`하여 문자열을 조합할 때 일반적으로 가장 적합합니다.
- **StringBuffer**도 Mutable하지만 주요 Method가 동기화되어 있어 여러 Thread에서 공유할 수 있습니다. 동기화 비용이 있으므로 Thread 안전성이 필요하지 않다면 StringBuilder가 일반적으로 더 효율적입니다.
- 예를 들어 반복문에서 많은 문자열을 이어 붙여야 한다면 `StringBuilder`를 생성하고 `append()`한 뒤 마지막에 `toString()`을 호출할 수 있습니다.
- 단순한 문자열 연결은 Java Compiler가 최적화할 수 있으므로 모든 `+` 연산을 무조건 StringBuilder로 바꾸기보다 반복 횟수와 실행 환경을 기준으로 선택해야 합니다.

참고 자료:
- https://docs.oracle.com/en/java/javase/26/docs/api/java.base/java/lang/String.html
- https://docs.oracle.com/en/java/javase/26/docs/api/java.base/java/lang/StringBuilder.html
- https://docs.oracle.com/en/java/javase/26/docs/api/java.base/java/lang/StringBuffer.html

---

## [ROLE-007] Java Collection Framework에서 List, Set, Map의 차이를 설명해 주세요.

답변:
- 쉽게 한 줄로 설명하면, **List는 순서가 있고 중복을 허용하며, Set은 중복을 허용하지 않고, Map은 Key와 Value의 쌍으로 데이터를 저장합니다.**
- **List**는 각 요소의 순서를 유지하고 Index로 접근할 수 있으며 같은 값을 여러 번 저장할 수 있습니다. 대표적인 구현체로 ArrayList와 LinkedList가 있습니다.
- **Set**은 중복된 요소를 저장하지 않습니다. 다만 순서 보장 방식은 구현체에 따라 달라서 HashSet은 순서를 보장하지 않고, LinkedHashSet은 삽입 순서를 유지하며, TreeSet은 정렬된 순서를 사용합니다.
- **Map**은 고유한 Key와 해당 Key에 연결된 Value를 저장합니다. Key는 중복될 수 없지만 서로 다른 Key에 같은 Value를 저장하는 것은 가능합니다.
- Map은 Collection Framework에 포함되지만 `Collection` Interface를 직접 상속하지는 않습니다.
- 예를 들어 장바구니처럼 순서와 중복이 필요하면 List, 중복 없는 태그 목록에는 Set, 회원 ID로 회원 정보를 조회하려면 Map을 사용할 수 있습니다.

참고 자료:
- https://docs.oracle.com/en/java/javase/26/docs/api/java.base/java/util/List.html
- https://docs.oracle.com/en/java/javase/26/docs/api/java.base/java/util/Set.html
- https://docs.oracle.com/en/java/javase/26/docs/api/java.base/java/util/Map.html

---

## [ROLE-008] ArrayList와 LinkedList의 차이를 설명하고, 각각 어떤 상황에서 유리한지 설명해 주세요.

답변:
- 쉽게 한 줄로 설명하면, **ArrayList는 크기가 늘어나는 배열이라 Index 조회에 유리하고, LinkedList는 앞뒤 Node를 연결한 이중 연결 리스트라 양 끝의 삽입과 삭제에 유리합니다.**
- **ArrayList**는 내부 배열에 요소를 Index 순서로 저장합니다. `get(index)`와 `set(index)`는 O(1)이고, 맨 뒤에 추가하는 `add()`는 배열 확장을 고려해도 평균적으로 Amortized O(1)입니다.
- ArrayList의 맨 앞이나 중간에 요소를 삽입하거나 삭제하면 뒤의 요소들을 이동해야 하므로 O(n)이 걸립니다.
- **LinkedList**는 각 Node가 요소와 이전·다음 Node의 연결 정보를 가집니다. `get(index)`는 Node를 순서대로 따라가야 하므로 O(n)입니다.
- LinkedList의 `addFirst()`, `addLast()`, `removeFirst()`, `removeLast()`처럼 양 끝에서 수행하는 연산은 O(1)입니다. 하지만 `add(index)`나 `remove(index)`는 해당 위치를 찾는 데 O(n)이 필요하므로 모든 삽입과 삭제가 무조건 빠른 것은 아닙니다.
- Index 조회가 많은 상품 목록에는 ArrayList가 적합하고, 양 끝에서 요소를 넣고 빼는 Deque 용도에는 LinkedList를 고려할 수 있습니다. 다만 Queue나 Stack 용도에는 일반적으로 ArrayDeque도 함께 비교하는 것이 좋습니다.
- 두 구현체 모두 기본적으로 Thread-safe하지 않으므로 여러 Thread가 동시에 수정한다면 별도의 동기화나 목적에 맞는 동시성 Collection이 필요합니다.

참고 자료:
- https://docs.oracle.com/en/java/javase/26/docs/api/java.base/java/util/ArrayList.html
- https://docs.oracle.com/en/java/javase/26/docs/api/java.base/java/util/LinkedList.html
- https://docs.oracle.com/en/java/javase/26/docs/api/java.base/java/util/doc-files/coll-reference.html

---

## [ROLE-009] HashMap의 동작 원리와 충돌이 발생했을 때 처리 방식에 대해 설명해 주세요.

답변:
- 쉽게 한 줄로 설명하면, **HashMap은 Key의 Hash 값을 이용해 저장할 Bucket을 찾고, 같은 Bucket에 여러 Key가 배정되는 충돌은 연결 리스트와 Tree 구조로 처리합니다.**
- `put()`은 Key의 `hashCode()`로 만든 Hash 값을 이용해 Bucket Index를 계산하고, Bucket이 비어 있으면 새로운 Entry를 저장합니다.
- Bucket에 이미 Entry가 있다면 Hash 값과 `equals()`를 확인합니다. 같은 Key이면 기존 Value를 교체하고, 다른 Key이면 같은 Bucket 안에 별도의 Entry로 저장합니다.
- 서로 다른 Key가 같은 Bucket에 배정되는 것을 Hash Collision이라고 합니다. 현재 OpenJDK 구현은 충돌한 Entry를 처음에는 연결 리스트로 관리하고, 충돌이 많아지면 Red-Black Tree로 전환하여 탐색 성능 저하를 줄입니다.
- 기본 Load Factor는 0.75이며 Entry 수가 임계값을 넘으면 Bucket 배열을 확장하고 Entry를 재배치합니다. Hash가 고르게 분산된다는 전제에서 `get()`과 `put()`은 평균 O(1)입니다.
- 사용자 정의 Key는 `equals()`가 `true`이면 반드시 같은 `hashCode()`를 반환하도록 구현해야 합니다. 저장한 뒤 Hash 계산에 사용한 Field를 변경하면 기존 Bucket에서 Key를 찾지 못할 수 있습니다.
- Tree 전환 기준 같은 세부 동작은 Map Interface의 보장이 아니라 OpenJDK HashMap의 구현 세부 사항이며, HashMap 자체는 Thread-safe하지 않습니다.

참고 자료:
- https://docs.oracle.com/en/java/javase/26/docs/api/java.base/java/util/HashMap.html
- https://docs.oracle.com/en/java/javase/26/docs/api/java.base/java/lang/Object.html#hashCode()
- https://github.com/openjdk/jdk/blob/master/src/java.base/share/classes/java/util/HashMap.java

---

## [ROLE-010] Java의 Garbage Collection이 무엇이고, 왜 필요한지 설명해 주세요.

답변:
- 쉽게 한 줄로 설명하면, **Garbage Collection은 더 이상 사용할 수 없는 객체를 JVM이 찾아 Heap 메모리를 자동으로 회수하고 재사용하게 하는 기능**입니다.
- Java에서 객체를 생성하면 Heap을 사용합니다. Garbage Collector는 GC Root에서 참조 경로를 따라 도달할 수 있는 Reachable 객체는 유지하고, 더 이상 도달할 수 없는 Unreachable 객체를 회수 대상으로 판단합니다.
- GC를 사용하면 개발자가 객체마다 메모리를 직접 해제하지 않아도 되므로 중복 해제나 이미 해제된 메모리 접근 같은 오류를 줄일 수 있습니다.
- 다만 객체가 Unreachable해졌다고 즉시 회수되는 것은 아니며, `System.gc()`도 GC 수행을 요청할 뿐 실행 시점을 보장하지 않습니다.
- 사용하지 않는 객체라도 `static List` 등에 참조가 계속 남아 있으면 GC가 살아 있는 객체로 판단하므로 Java에서도 Memory Leak과 `OutOfMemoryError`가 발생할 수 있습니다.
- GC는 File, Socket, DB Connection 같은 외부 자원의 즉시 반납을 보장하지 않습니다. 이러한 자원은 `try-with-resources`나 명시적인 `close()`로 관리해야 합니다.
- GC에는 CPU 사용과 Pause 비용이 있으므로 Application의 Latency, Throughput, Heap 크기에 맞는 Collector와 설정을 선택하고 GC Log와 Metric을 확인해야 합니다.

참고 자료:
- https://docs.oracle.com/en/java/javase/26/gctuning/introduction-garbage-collection-tuning.html
- https://docs.oracle.com/en/java/javase/26/docs/api/java.base/java/lang/ref/package-summary.html
- https://docs.oracle.com/en/java/javase/26/docs/api/java.base/java/lang/System.html#gc()

---

## [ROLE-011] Spring Framework가 무엇이고, Spring을 사용하는 이유를 설명해 주세요.

답변:
- 쉽게 한 줄로 설명하면, **Spring Framework는 객체 생성과 연결, Transaction, Web 요청 처리 같은 공통 기능을 제공하여 개발자가 비즈니스 로직에 집중할 수 있게 하는 Java Application Framework**입니다.
- Spring의 중심에는 IoC Container와 DI가 있습니다. `ApplicationContext`가 설정 정보를 바탕으로 Bean을 생성하고 의존 관계와 생명주기를 관리합니다.
- 객체가 필요한 구현체를 직접 생성하지 않고 외부에서 주입받게 만들 수 있으므로 구현체 교체와 단위 테스트가 쉬워지고 결합도를 낮추는 데 도움이 됩니다.
- Spring은 Core Container뿐 아니라 AOP, Event, Validation, Data Access와 Transaction 추상화, Spring MVC, Spring WebFlux, Test 지원 등을 모듈 형태로 제공합니다.
- Transaction은 JDBC, JPA 같은 기술이 달라도 일관된 방식으로 관리할 수 있고, 선언적 Transaction을 사용하면 반복적인 시작·Commit·Rollback 코드를 비즈니스 로직과 분리할 수 있습니다.
- 예를 들어 `OrderService`가 생성자로 `PaymentClient`를 받게 만들면 운영 환경에서는 실제 결제 Bean을, 단위 테스트에서는 Fake 구현체를 주입하기 쉽습니다.
- Spring Framework는 핵심 Application 기능을 제공하고, Spring Boot는 그 위에서 Auto Configuration, Starter, 실행 환경을 제공하여 설정과 실행을 간소화합니다.

참고 자료:
- https://spring.io/projects/spring-framework/
- https://docs.spring.io/spring-framework/reference/overview.html
- https://docs.spring.io/spring-framework/reference/core/beans/introduction.html

---

## [ROLE-012] Spring의 IoC와 DI가 무엇인지 설명해 주세요.

답변:
- 쉽게 한 줄로 설명하면, **IoC는 객체 생성과 관리의 주도권을 Spring Container에 맡기는 원칙이고, DI는 객체가 필요한 의존성을 외부에서 주입받는 IoC 구현 방법**입니다.
- IoC가 적용되지 않은 객체는 필요한 구현체를 직접 `new`로 생성하거나 찾아야 합니다. Spring에서는 `ApplicationContext`가 설정 정보를 읽고 Bean의 생성, 의존 관계 연결, 생명주기를 관리합니다.
- DI를 사용하면 객체는 필요한 의존성을 생성자, Factory Method, Setter, Field 등을 통해 Container로부터 전달받습니다.
- 예를 들어 `OrderService`가 생성자로 `OrderRepository`를 받도록 작성하면 Spring이 해당 Type의 Bean을 찾아 `OrderService`를 생성할 때 주입합니다.
- 객체가 구현체를 직접 생성하지 않으므로 결합도가 낮아지고, Interface에 의존하면 구현체 교체와 단위 테스트에서 Fake나 Mock을 주입하기 쉬워집니다.
- 같은 Type의 Bean이 여러 개이면 Spring이 하나를 선택할 수 없으므로 `@Primary`나 `@Qualifier` 등으로 주입 대상을 명확히 지정해야 합니다.

참고 자료:
- https://docs.spring.io/spring-framework/reference/core/beans/introduction.html
- https://docs.spring.io/spring-framework/reference/core/beans/basics.html
- https://docs.spring.io/spring-framework/reference/core/beans/dependencies/factory-collaborators.html

---

## [ROLE-013] @Component, @Controller, @RestController, @Service, @Repository의 역할과 차이를 설명해 주세요.

답변:
- 쉽게 한 줄로 설명하면, **모두 Spring이 관리할 Component를 나타내지만 각 Annotation은 일반 객체, 요청 처리, 비즈니스 로직, 데이터 접근이라는 역할을 구분합니다.**
- **`@Component`**는 특정 계층에 한정되지 않는 일반적인 Spring Component에 사용합니다.
- **`@Controller`**는 Spring MVC에서 HTTP 요청을 처리하는 Controller에 사용합니다. 일반적으로 반환값을 View 이름으로 해석하며, `@ResponseBody`를 사용하면 응답 본문에 값을 작성할 수 있습니다.
- **`@RestController`**는 `@Controller`와 `@ResponseBody`를 합친 조합 Annotation으로, 반환값이 기본적으로 JSON 같은 HTTP 응답 본문으로 변환됩니다.
- **`@Service`**는 비즈니스 규칙과 Use Case를 처리하는 Service 계층임을 나타냅니다. Annotation 자체가 Transaction을 자동으로 적용하는 것은 아닙니다.
- **`@Repository`**는 Persistence 계층을 나타냅니다. 관련 후처리기와 Translator가 적용된 환경에서는 기술별 Persistence Exception을 Spring의 `DataAccessException` 계층으로 변환하는 데 참여할 수 있습니다.
- `@Controller`, `@Service`, `@Repository`는 `@Component`의 특수화 Annotation이고 `@RestController`는 `@Controller`를 포함하므로, Component Scan 대상에 포함되면 Spring Bean으로 등록됩니다.

참고 자료:
- https://docs.spring.io/spring-framework/reference/core/beans/classpath-scanning.html
- https://docs.spring.io/spring-framework/docs/current/javadoc-api/org/springframework/web/bind/annotation/RestController.html
- https://docs.spring.io/spring-framework/docs/current/javadoc-api/org/springframework/stereotype/Repository.html

---

## [ROLE-014] @Autowired와 생성자 주입의 차이를 설명하고, 생성자 주입이 권장되는 이유를 설명해 주세요.

답변:
- 쉽게 한 줄로 설명하면, **`@Autowired`는 Spring에 주입 지점을 알려 주는 Annotation이고, 생성자 주입은 객체 생성 시 필요한 의존성을 생성자 인자로 전달하는 DI 방식**입니다.
- `@Autowired`는 생성자뿐 아니라 Field, Setter, 일반 Method에도 사용할 수 있으므로 `@Autowired`와 Field 주입을 같은 의미로 보면 안 됩니다.
- 생성자 주입에도 `@Autowired`를 사용할 수 있지만 Class에 생성자가 하나만 있다면 Spring이 그 생성자를 자동으로 사용하므로 생략할 수 있습니다.
- 생성자 주입은 필수 의존성이 생성자 Signature에 드러나고, 누락을 Bean 생성 시점에 발견하여 완전히 초기화된 객체만 사용하게 합니다.
- 주입받은 Field를 `final`로 선언할 수 있고, 테스트에서도 `new OrderService(fakeRepository)`처럼 Spring Container 없이 객체를 쉽게 생성할 수 있습니다.
- Field 주입은 의존성이 외부에 잘 드러나지 않고 일반 생성만으로 완전한 객체를 만들기 어려우며, Container 없는 테스트에서 Reflection 같은 추가 작업이 필요할 수 있습니다.
- 생성자 인자가 지나치게 많다면 Class가 너무 많은 책임을 가지고 있다는 신호일 수 있습니다. 순환 의존성도 Field 주입으로 숨기기보다 책임을 분리해 해결하는 것이 좋습니다.

참고 자료:
- https://docs.spring.io/spring-framework/reference/core/beans/annotation-config/autowired.html
- https://docs.spring.io/spring-framework/reference/core/beans/dependencies/factory-collaborators.html
- https://docs.spring.io/spring-framework/docs/current/javadoc-api/org/springframework/beans/factory/annotation/Autowired.html

---

## [ROLE-015] Spring Bean이 무엇이고, Bean 생명주기에 대해 설명해 주세요.

답변:
- 쉽게 한 줄로 설명하면, **Spring Bean은 IoC Container가 생성하고 의존성을 연결하며 초기화와 소멸까지 관리하는 객체**입니다.
- Bean은 `@Component` 계열 Annotation, `@Bean` Method, XML 등의 설정으로 등록할 수 있습니다. 기본 Scope는 Singleton이며, 이는 하나의 IoC Container 안에서 Bean Definition당 하나의 인스턴스를 공유한다는 뜻입니다.
- 일반적인 생성 과정은 **Bean Definition 확인 → 객체 생성 → 의존성 주입 → Aware Callback → 초기화 전 BeanPostProcessor → 초기화 Callback → 초기화 후 BeanPostProcessor → 사용 가능 상태** 순서입니다.
- 초기화 Callback에는 `@PostConstruct`, `InitializingBean.afterPropertiesSet()`, 별도로 설정한 `init-method` 등이 있습니다. 여러 방식을 함께 사용하면 일반적으로 이 순서대로 호출됩니다.
- 초기화 후 BeanPostProcessor 단계에서 AOP Proxy 등으로 감싸진 객체가 최종 Bean으로 제공될 수 있습니다.
- Container가 정상적으로 종료되면 `@PreDestroy`, `DisposableBean.destroy()`, 별도로 설정한 `destroy-method` 등의 소멸 Callback을 실행합니다. 강제 종료 시에는 실행이 보장되지 않습니다.
- Prototype Scope는 Container가 생성과 초기화까지만 담당하고 소멸 Callback을 자동으로 호출하지 않으므로 Client가 필요한 자원을 직접 정리해야 합니다.

참고 자료:
- https://docs.spring.io/spring-framework/docs/current/javadoc-api/org/springframework/beans/factory/BeanFactory.html
- https://docs.spring.io/spring-framework/reference/core/beans/factory-nature.html
- https://docs.spring.io/spring-framework/reference/core/beans/factory-scopes.html

---

## [ROLE-016] Spring MVC 요청 처리 흐름을 DispatcherServlet 중심으로 설명해 주세요.

답변:
- 쉽게 한 줄로 설명하면, **DispatcherServlet은 Spring MVC 요청을 먼저 받아 적절한 Controller로 전달하고 응답 생성까지 조정하는 Front Controller**입니다.
- 요청 처리 흐름은 다음과 같습니다.
  1. Client의 HTTP 요청이 Servlet Container와 Filter Chain을 거쳐 `DispatcherServlet`에 도착합니다.
  2. `DispatcherServlet`은 `HandlerMapping`을 통해 요청 URL과 HTTP Method를 처리할 Handler와 적용할 Interceptor를 찾습니다.
  3. 선택된 Handler를 실행할 수 있는 `HandlerAdapter`가 요청 Parameter와 Body를 Controller Method의 인자로 변환하고 Controller를 호출합니다.
  4. Controller는 Service 등을 호출한 뒤 View 이름이나 응답 객체를 반환합니다.
  5. REST API는 `HttpMessageConverter`가 반환 객체를 JSON 같은 응답 Body로 변환하고, 화면을 반환하는 MVC는 `ViewResolver`가 View를 찾아 Rendering합니다.
  6. 만들어진 HTTP 응답이 `DispatcherServlet`과 Filter Chain을 거쳐 Client에게 전달됩니다.
- 처리 중 예외가 발생하면 `HandlerExceptionResolver`가 `@ExceptionHandler`, `@ControllerAdvice` 등의 처리 방법을 찾아 응답으로 변환할 수 있습니다.
- DispatcherServlet은 비즈니스 로직을 직접 수행하기보다 요청 Mapping, Handler 실행, 응답 변환을 각 구성 요소에 위임하고 전체 흐름을 조정합니다.

참고 자료:
- https://docs.spring.io/spring-framework/reference/web/webmvc/mvc-servlet.html
- https://docs.spring.io/spring-framework/reference/web/webmvc/mvc-servlet/sequence.html
- https://docs.spring.io/spring-framework/reference/web/webmvc/message-converters.html

---

## [ROLE-017] Controller, Service, Repository 계층의 역할과 분리하는 이유를 설명해 주세요.

답변:
- 쉽게 한 줄로 설명하면, **Controller는 HTTP 요청과 응답, Service는 비즈니스 로직, Repository는 데이터 저장과 조회를 담당하도록 관심사를 나누는 방식**입니다.
- **Controller**는 URL과 HTTP Method를 Mapping하고 요청값 검증, DTO 변환, 응답 상태와 형식 결정을 담당합니다. 핵심 비즈니스 로직은 가능한 한 Controller에 두지 않습니다.
- **Service**는 회원 가입이나 주문 생성 같은 비즈니스 Use Case를 수행하며, 여러 Repository나 외부 API를 조합하고 Transaction 경계를 관리할 수 있습니다.
- **Repository**는 Entity의 저장과 조회 같은 데이터 접근을 추상화하여 상위 계층이 JPA나 SQL의 세부 구현에 직접 의존하지 않도록 합니다.
- 계층을 분리하면 각 Class의 책임이 작아지고 비즈니스 로직을 HTTP나 DB 구현과 분리하여 테스트하기 쉬워집니다. API 형식이나 저장 방식이 바뀔 때 변경 영향도 줄일 수 있습니다.
- 예를 들어 `MemberController`가 회원 가입 요청을 받고, `MemberService`가 중복 확인과 회원 생성 규칙을 수행하며, `MemberRepository`가 회원을 DB에 저장할 수 있습니다.
- Controller-Service-Repository 구조는 Spring이 강제하는 규칙이 아니라 널리 사용하는 설계 관례입니다. 모든 요청에 의미 없는 계층을 추가하기보다 Project와 Domain의 복잡도에 맞게 구성해야 합니다.

참고 자료:
- https://docs.spring.io/spring-boot/reference/using/structuring-your-code.html
- https://docs.spring.io/spring-data/jpa/reference/repositories/core-concepts.html
- https://docs.spring.io/spring-framework/reference/data-access/transaction/declarative.html

---

## [ROLE-018] DTO를 사용하는 이유와 Entity를 API 응답으로 직접 반환하지 않는 이유를 설명해 주세요.

답변:
- 쉽게 한 줄로 설명하면, **DTO는 API에 필요한 데이터만 전달하여 외부 API 계약과 내부 Entity 구조를 분리하기 위해 사용합니다.**
- Entity는 영속성 Context에서 상태가 관리되는 Domain 객체이고, DTO는 계층이나 Process 사이에서 필요한 값을 전달하기 위한 객체입니다.
- 요청 DTO를 사용하면 Client에게 입력받을 Field를 명확히 제한하고 각 요청에 맞는 Validation을 적용할 수 있습니다.
- 응답 DTO를 사용하면 `passwordHash`, 내부 권한, 관리용 상태처럼 공개하면 안 되는 Field를 제외하고 필요한 데이터만 반환할 수 있습니다.
- Entity를 직접 반환하면 Entity Field 변경이 API 응답 형식 변경으로 이어져 DB 구조와 API가 강하게 결합됩니다. 연관 Entity가 의도치 않게 직렬화되거나 Lazy Loading, 순환 참조, 과도한 Query 문제가 생길 수도 있습니다.
- 요청 Body를 Entity에 바로 Binding하면 Client가 수정하면 안 되는 권한이나 상태까지 전달하는 Mass Assignment 문제가 발생할 수 있습니다. DTO로 허용 Field를 제한하되 Validation과 권한 검사도 함께 수행해야 합니다.
- DTO Mapping 코드가 늘어난다는 비용은 있지만 API 안정성, 보안 검토, 계층 간 결합도 감소라는 장점이 있습니다.

참고 자료:
- https://owasp.org/www-project-web-security-testing-guide/latest/4-Web_Application_Security_Testing/12-API_Testing/03-Testing_for_Excessive_Data_Exposure
- https://cheatsheetseries.owasp.org/cheatsheets/Mass_Assignment_Cheat_Sheet.html
- https://docs.spring.io/spring-data/jpa/reference/repositories/projections.html

---

## [ROLE-019] Spring Boot가 기존 Spring Framework와 비교해 제공하는 장점을 설명해 주세요.

답변:
- 쉽게 한 줄로 설명하면, **Spring Boot는 Spring Framework를 기반으로 반복적인 설정과 배포 준비를 자동화하여 Spring Application을 빠르게 실행하게 해주는 도구**입니다.
- Spring Framework는 IoC, DI, AOP, MVC, Transaction 같은 핵심 기능을 제공하고, Spring Boot는 이 기능들을 더 편리하게 구성하고 실행하도록 지원합니다. 따라서 Spring Boot가 Spring Framework를 대체하는 것은 아닙니다.
- **Auto Configuration**은 Classpath의 Library와 사용자가 등록한 Bean 등을 기준으로 필요한 기본 설정을 자동 구성합니다. 사용자가 직접 Bean을 등록하여 필요한 부분을 바꿀 수도 있습니다.
- **Starter Dependency**는 Web, JPA, Security처럼 자주 함께 사용하는 Dependency를 목적별로 묶어 제공하므로 Library 선택과 Version 관리 부담을 줄입니다.
- Tomcat 같은 **Embedded Server**를 포함할 수 있어 별도의 WAS에 WAR를 배포하지 않고 실행 가능한 JAR를 `java -jar`로 실행할 수 있습니다.
- 외부 설정, Profile, Logging 등의 기본 구성을 제공하며 Actuator를 추가하면 Health Check, Metric 같은 운영 기능을 사용할 수 있습니다.
- 자동 설정을 이해하지 못하면 동작이 숨겨져 있다고 느낄 수 있으므로 Condition Report로 적용된 설정을 확인하고 필요한 Auto Configuration을 Override하거나 제외할 수 있어야 합니다.

참고 자료:
- https://spring.io/projects/spring-boot/
- https://docs.spring.io/spring-boot/reference/using/auto-configuration.html
- https://docs.spring.io/spring-boot/reference/actuator/

---

## [ROLE-020] application.yml 또는 application.properties의 역할과 Profile을 사용하는 이유를 설명해 주세요.

답변:
- 쉽게 한 줄로 설명하면, **Application 설정 파일은 실행 환경에 따라 달라지는 값을 코드 밖에서 관리하고, Profile은 개발·테스트·운영 환경별 설정과 Bean을 선택하기 위해 사용합니다.**
- `application.yml`과 `application.properties`에는 Server Port, DB 접속 정보, Logging Level, 외부 API 주소처럼 Application 실행에 필요한 설정을 작성할 수 있습니다.
- 설정값은 `@Value`, Spring의 `Environment`, `@ConfigurationProperties` 등을 통해 사용할 수 있습니다. 구조화된 여러 설정에는 Type 검증과 관리가 쉬운 `@ConfigurationProperties`가 유용합니다.
- 공통 설정은 `application.yml`에 두고 환경별 설정은 `application-local.yml`, `application-test.yml`, `application-prod.yml`처럼 분리할 수 있습니다. `@Profile`로 특정 환경에서만 Bean을 등록할 수도 있습니다.
- 예를 들어 Local Profile에서는 Local DB와 상세 Logging을 사용하고, Production Profile에서는 운영 DB와 필요한 수준의 Logging만 사용하도록 구성할 수 있습니다.
- 설정값이 여러 위치에 있으면 Spring Boot의 PropertySource 우선순위에 따라 높은 우선순위의 값이 기존 값을 덮어쓰므로 실제 적용 순서를 확인해야 합니다.
- Profile은 보안 경계가 아닙니다. Password나 API Key 같은 Secret을 Git에 포함된 설정 파일에 직접 기록하지 말고 Secret Manager나 배포 환경에서 안전하게 주입해야 합니다.

참고 자료:
- https://docs.spring.io/spring-boot/reference/features/external-config.html
- https://docs.spring.io/spring-boot/reference/features/profiles.html
- https://cheatsheetseries.owasp.org/cheatsheets/Secrets_Management_Cheat_Sheet.html

---

## 선택 질문

## [ROLE-021] Java의 Checked Exception과 Unchecked Exception의 차이를 설명해 주세요.

답변:

참고 자료:

---

## [ROLE-022] Java에서 final 키워드가 변수, 메서드, 클래스에 사용될 때 각각 어떤 의미인지 설명해 주세요.

답변:

참고 자료:

---

## [ROLE-023] Java Stream API가 무엇이고, for문과 비교했을 때 장단점을 설명해 주세요.

답변:

참고 자료:

---

## [ROLE-024] Optional을 사용하는 이유와 잘못 사용할 수 있는 예시를 설명해 주세요.

답변:

참고 자료:

---

## [ROLE-025] Java의 Generic이 무엇이고, 사용하는 이유를 설명해 주세요.

답변:

참고 자료:

---

## [ROLE-026] Java에서 동시성 문제가 발생하는 이유와 synchronized, volatile의 차이를 설명해 주세요.

답변:

참고 자료:

---

## [ROLE-027] Thread Pool이 무엇이고, Java에서 ExecutorService를 사용하는 이유를 설명해 주세요.

답변:

참고 자료:

---

## [ROLE-028] Spring AOP가 무엇이고, 어떤 상황에서 사용할 수 있는지 설명해 주세요.

답변:

참고 자료:

---

## [ROLE-029] @Transactional이 동작하는 원리와 주의해야 할 점을 설명해 주세요.

답변:

참고 자료:

---

## [ROLE-030] JPA가 무엇이고, MyBatis와 비교했을 때 어떤 차이가 있는지 설명해 주세요.

답변:

참고 자료:

---

## [ROLE-031] JPA의 영속성 컨텍스트가 무엇이고, 1차 캐시, 변경 감지, 쓰기 지연에 대해 설명해 주세요.

답변:

참고 자료:

---

## [ROLE-032] JPA에서 Lazy Loading과 Eager Loading의 차이를 설명해 주세요.

답변:

참고 자료:

---

## [ROLE-033] JPA N+1 문제가 무엇이고, Fetch Join, EntityGraph, Batch Size로 해결하는 방법을 설명해 주세요.

답변:

참고 자료:

---

## [ROLE-034] Spring Security의 기본 인증 흐름을 설명해 주세요.

답변:

참고 자료:

---

## [ROLE-035] JWT 기반 인증을 Spring Security에서 구현할 때 Filter가 어떤 역할을 하는지 설명해 주세요.

답변:

참고 자료:

---

## [ROLE-036] REST API 설계 시 Request DTO, Response DTO, Error Response를 어떻게 설계하면 좋은지 설명해 주세요.

답변:

참고 자료:

---

## [ROLE-037] Spring에서 예외 처리를 전역으로 관리하는 방법과 @ControllerAdvice, @ExceptionHandler의 역할을 설명해 주세요.

답변:

참고 자료:

---

## [ROLE-038] 백엔드 API 성능이 느릴 때 어떤 순서로 원인을 분석하고 개선할 수 있는지 설명해 주세요.

답변:

참고 자료:

---

## [ROLE-039] Spring 애플리케이션에서 캐시를 적용할 때 고려해야 할 점을 설명해 주세요.

답변:

참고 자료:

---

## [ROLE-040] Spring 백엔드 프로젝트에서 테스트 코드를 작성할 때 단위 테스트, 슬라이스 테스트, 통합 테스트를 어떻게 구분할 수 있는지 설명해 주세요.

답변:

참고 자료:
