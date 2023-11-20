# Domain Model

## ✅ Domain Model 이란

도메인 모델은 특정 문제 영역을 개념적으로 모델링한 것입니다.

소프트웨어 개발에서 도메인 모델은 해당 도메인의 주요개념, 엔티티, 엔티티 간의 관계, 규칙 등을 포함합니다.

이 모델은 복잡한 비즈니스 로직이나 비즈니스 프로세스를 이해하고, 시스템이 해결해야 할 실제 문제를 반영하는 데 도움을 줍니다.



### 도메인 모델의 특징

추상화: 도메인 모델은 실제 세계의 복잡성을 추상화하여 간단하고 이해하기 쉬운 형태로 표현합니다.

엔티티와 관계: 모델은 도메인 내의 주요 엔티티와 이들 간의 관계를 나타냅니다.



## ✅ Repository

데이터베이스에 직접적으로 접근합니다.

```java
import org.springframework.data.jpa.repository.JpaRepository;
import org.springframework.stereotype.Repository;

@Repository
public interface UserRepository extends JpaRepository<User, Long> {
    // 사용자 정의 메소드
    User findByUsername(String username);
}

```

자바 Spring Boot 에서는 위와 같이 구현한다.

Repository 패턴은 데이터 접근 로직을 분리하고,&#x20;

애플리케이션의 다른 부분과의 결합도를 낮추는 데 도움을 준다.

## ✅ VO(Value Object)

VO는 데이터를 담는 객체로, 여러 속성을 하나의 단위로 묶어 표현한다.

1. **불변성(Immutability):** VO는 생성 시점에 설정된 데이터를 변경할 수 없습니다. 데이터가 변경되어야 할 경우, 새로운 VO 인스턴스가 생성됩니다.
2. **동등성(Equality):** VO의 동등성은 객체의 참조가 아닌, 객체가 담고 있는 데이터의 값으로 결정됩니다. 즉, 같은 값을 가진 두 VO 객체는 동일하게 취급됩니다.
3. **자체 완결성(Self-contained):** VO는 비즈니스 로직을 포함할 수 있으며, 이를 통해 데이터와 관련된 행위를 함께 캡슐화합니다.
4. **재사용성(Reusability):** VO는 다양한 모델이나 계층에서 재사용될 수 있습니다.
