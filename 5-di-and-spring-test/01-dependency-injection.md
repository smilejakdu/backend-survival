# 01-Dependency Injection



## ✅ Spring AOP(Aspect Oriented Programming)



### 📌 AOP 란 뭘까 ??

AOP 는 Spring 에서만 국한되어있는 용어는 아니다.

관점 지향 프로그래밍이라서 객체 지향 프로그래밍에 자주 사용하는 용어이다.

로직을 핵심적인 관점, 부가적인 관점으로 나누어서 각각 모듈화를 한다.

왜 ?? 나누어서 모듈화하는데 ?

Aspect 로 모듈화하고 핵심적인 비즈니스 로직에서 분리하여 재사용하겠다는 것이 AOP 의 취지이다.

### 📌 그러면 Spring AOP 는 뭐야 ?

Spring AOP를 사용하면 애플리케이션의 여러 부분에서 반복적으로 사용되는 공통 기능을 별도의 모듈로 분리하여 관리할 수 있다. 이러한 공통 기능에는 로깅, 트랜잭션 관리, 보안 검사 등이 포함될 수 있다.

1. **관점(Aspect)**: 공통 기능을 모듈화한 것을 관점이라고 합니다. 예를 들어, 로깅이나 보안 검사를 하나의 관점으로 정의할 수 있습니다.
2. **어드바이스(Advice)**: 관점이 어떤 시점에서 실행될지를 정의합니다. 예를 들어, 메서드 실행 전(pre-advice), 실행 후(post-advice), 예외 발생 시(after-throwing advice) 등 다양한 시점에 대한 처리를 정의할 수 있습니다.
3. **포인트컷(Pointcut)**: 어드바이스가 적용될 대상(메서드나 클래스)을 지정합니다. 표현식을 사용하여 특정 조건을 만족하는 메서드에 어드바이스를 적용할 수 있습니다.
4. **조인 포인트(Join Point)**: 애플리케이션 실행 중 어드바이스가 적용될 수 있는 지점, 예를 들어 메서드 호출이나 객체 생성 등입니다.
5. **프록시 기반**: Spring AOP는 프록시 기반의 AOP를 구현합니다. 이는 대상 객체에 대한 프록시를 생성하여 어드바이스를 적용합니다. 이는 주로 메서드 호출을 가로채는 방식으로 이루어집니다.

개념적으로는 위와 같고 코드로 한번 살펴보자.

{% embed url="https://adjh54.tistory.com/133#3.%20%ED%8C%A8%ED%82%A4%EC%A7%80%EC%99%80%20%ED%8C%8C%EC%9D%BC%EC%9D%84%20%EA%B5%AC%EC%84%B1%ED%95%A9%EB%8B%88%EB%8B%A4-1" %}

예시는 위의 블로그에서 간단히 잘 나와있다.

`build.gradle` 에 Gradle: org.springframework.boot:spring-boot-starter-aop:version

을 의존성 추가한다.

<figure><img src="../.gitbook/assets/스크린샷 2023-11-28 오후 11.16.35.png" alt="" width="364"><figcaption></figcaption></figure>

`@Aspect` 어노테이션을 추가

```java
package com.projectName.multiflexapi.aspect;

import org.aspectj.lang.annotation.Aspect;
import org.springframework.stereotype.Component;

/**
 * 로깅 관련 AOP 구성
 *
 * @author : jonghoon
 * @fileName : LoggingAspect
 * @since : 2023/03/01
 */
@Aspect
@Component
public class LoggingAspect {

}

```

* `@Before` : 대상 메서드가 실행되기 전에 Advice 를 실행한다.
* `@After` : 대상 메서드가 실행된 후에 Advice를 실행한다.
* `@AfterReturning` : 대상 메서드가 정상적으로 실행되고 반환된 후에 Advice 를 실행한다.
* `@AfterThrowing` : 대상 메서드에서 예외가 발생 했을때 Advice 를 실행한다.
* `@Around` : 대상 메서드 실행 전, 후 또는 예외 발생 시에 Advice 를 실행한다.

```java
package com.adjh.multiflexapi.aspects;

import lombok.extern.slf4j.Slf4j;
import org.aspectj.lang.JoinPoint;
import org.aspectj.lang.ProceedingJoinPoint;
import org.aspectj.lang.annotation.*;
import org.springframework.stereotype.Component;

/**
 * 로깅 관련 AOP 구성
 *
 * @author : jonghoon
 * @fileName : LoggingAspect
 * @since : 2023/03/01
 */
@Aspect
@Component // 
@Slf4j // 로깅에 대한 추상 레이어를 제공하는 인터페이스의 모음 ex ) log.info();
public class LoggingAspect {

    /**
     * Before: 대상 “메서드”가 실행되기 전에 Advice를 실행합니다.
     *
     * @param joinPoint
     */
    @Before("execution(* com.adjh.multiflexapi.controller.*.*(..))")
    public void logBefore(JoinPoint joinPoint) {
        log.info("Before: " + joinPoint.getSignature().getName());
    }

    /**
     * After : 대상 “메서드”가 실행된 후에 Advice를 실행합니다.
     *
     * @param joinPoint
     */
    @After("execution(* com.adjh.multiflexapi.controller.*.*(..))")
    public void logAfter(JoinPoint joinPoint) {
        log.info("After: " + joinPoint.getSignature().getName());
    }

    /**
     * AfterReturning: 대상 “메서드”가 정상적으로 실행되고 반환된 후에 Advice를 실행합니다.
     *
     * @param joinPoint
     * @param result
     */
    @AfterReturning(pointcut = "execution(* com.adjh.multiflexapi.controller.*.*(..))", returning = "result")
    public void logAfterReturning(JoinPoint joinPoint, Object result) {
        log.info("AfterReturning: " + joinPoint.getSignature().getName() + " result: " + result);
    }

    /**
     * AfterThrowing: 대상 “메서드에서 예외가 발생”했을 때 Advice를 실행합니다.
     *
     * @param joinPoint
     * @param e
     */
    @AfterThrowing(pointcut = "execution(* com.adjh.multiflexapi.controller.*.*(..))", throwing = "e")
    public void logAfterThrowing(JoinPoint joinPoint, Throwable e) {
        log.info("AfterThrowing: " + joinPoint.getSignature().getName() + " exception: " + e.getMessage());
    }

    /**
     * Around : 대상 “메서드” 실행 전, 후 또는 예외 발생 시에 Advice를 실행합니다.
     *
     * @param joinPoint
     * @return
     * @throws Throwable
     */
    @Around("execution(* com.adjh.multiflexapi.controller.*.*(..))")
    public Object logAround(ProceedingJoinPoint joinPoint) throws Throwable {
        log.info("Around before: " + joinPoint.getSignature().getName());
        Object result = joinPoint.proceed();
        log.info("Around after: " + joinPoint.getSignature().getName());
        return result;
    }

}
```









*
* Dependency Injection
* 싱글턴 패턴
* IoC(Inversion of Control)
* Spring Bean
* BeanFactory
