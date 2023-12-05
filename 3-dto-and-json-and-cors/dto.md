---
description: Data Transfer Obje
---

# Dto



## DTO (Data Transfer Object) 란

When you're working with a remote interface, such as Remote Facade,

each call to it is expensive.

* IPC(Inter-Process Communication)
  * 서로 다른 프로세스, 거칠 게 이야기하면 서로 다른 프로그램이 서로 통신
  * B/E 와 F/E 로 Tier를 나누면 IPC가 필수적이다.
  * IPC에서 쓸 수 있는 기술
    * File -> 가장 기본적인 접근. 원격 환경에서 활용하기 어렵다.
    * Socket -> 파일과 유사하게 읽고 쓸 수 있지만, 원격 환경에서도 활용할 수 있다.
    * RPC
* DTO
  * 아주 단순하게 보면 Setter 와 Getter로만 이뤄짐.
  * private 된 필드와 setter 와 getter
  * JavaBeans에서 유래한 Java Bean 또는 그냥 Bean이라고 부르는 형태에 가까움 ( Spring Bean )\
    POJO 와 다름에 주의 하자 .
    * [https://ko.wikipedia.org/wiki/자바빈즈](https://ko.wikipedia.org/wiki/%EC%9E%90%EB%B0%94%EB%B9%88%EC%A6%88)
  * 제대로 된 객체가 아니라 그냥 무기력한 데이터 덩어리. C/C++ 등에선 구조체(struct)로 구분할 수 있지만, Java에선 불가능. 최신 Java에선 record를 활용할 수 있지만, 오래된 Bean 관련 라이브러리에선 지원하지 않음
* Tier 간 통신
  * F/E 와 B/E 사이
    * DTO 자체를 그대로 전송할 수는 없고, 직렬화(마샬링)를 통해야 한다.
    * 어떤 직렬화 기술을 사용할 건지도 결정해야 함. -> XML,  JSON
  * B/E 와 DB 사이
    * 아주 옛날에는 Value Object 를 DTO 란 의미로 썼지만, 재빨리 Transfer Object 라고 정정함.\
      아직도 한국의 오래된 SI 기업에서는 VO 를 DTO 란 의미로 사용 ( DAO 와 VO를 쓰고 있다면 대부분 여기에 속함 )&#x20;
    * JPA 를 지양하고 DDD 를 따르는 사람 중 일부는 ORM( JPA, 하이버네이트) 은 Active Record + DTO 처럼 접근&#x20;
    * 아샬은 Kotlin 과 Exposed 를 쓸 때도 이렇게 접근함.&#x20;

Data Transfer 란 측면에 집중하면, 원격(remote) 이 아닌 경우에도 DTO를 사용할 수 있다.





