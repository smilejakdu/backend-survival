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
