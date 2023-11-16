---
description: Data Transfer Obje
---

# Dto

DTO (Data Transfer Object) 란

When you're working with a remote interface, such as Remote Facade,

each call to it is expensive.

* 제약조건&#x20;
  * Between Processes
  * working with a remote interface, such as Remote Facade
  * 다른 프로세스와 통신, 그것도 원격(네트워크를 통해) 으로 !&#x20;
* IPC(Inter-Process Communication)
  * https://ko.wikipedia.org/wiki/프로세스\_같\_통신
  * 서로 다른 프로세스, 거칠 게 이야기하면 서로 다른 프로그램이 서로 통신
  * B/E 와 F/E 로 Tier를 나누면 IPC가 필수적이다.
  * IPC에서 쓸 수 있는 기술
    * File -> 가장 기본적인 접근. 원격 환경에서 활용하기 어렵다.
    * Socket -> 파일과 유사하게 읽고 쓸 수 있지만, 원격 환경에서도 활용할 수 있다.
    * RPC
* 프로세스 간 통신(IPC, Inter-Process Communication)
* “무기력한 도메인 모델” 이란 그리고 안티 패턴인 이유
* 자바빈즈(JavaBeans)
* EJB(Enterprise JavaBeans)
* Java의 record
* DAO
* ORM





