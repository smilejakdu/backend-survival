# Layered Architecture

## 강의 내용

## Separation of Concerns

관심사의 분리가 중요하다.

커다란 프로그램은 유지보수가 어렵다.

인간의 한계 + 공간의 한계.

유지보수가 가능하도록 적절하게 나누고,

그룹화해야한다. 파일 시스템의 폴더나 Java 의 패키지 등이 이를 위해 존재한다.

그리고 우리는 관심사 분리를 하게되고

관심사의 분리를 한다고 해서 무조건 좋은것은 아니다.

동전의 양면이 존재한다.

응집도가 높아지게 되면 결합도는 낮아지게 되는데,

A 에서 B 와 연관관계가 높다고 한다면 응집도가 낮게 구현하게 됐을때

에러가 날 확률이 높다.

왜냐면 A 응집도 B 응집도 각각 응집도가 높은것 끼리 결합하게되면 안맞을 수도 있다.

이러한 최소한의 이슈를 고려해서

Layered Architecture 로 구현한다.

## Layered Architecture

https://ko.wikipedia.org/wiki/다층\_구조

https://github.com/ahastudio/til/blob/main/architecture/layered-architecture.md

웹은 UI Layer 에서 다루고 , 그리고 Spring Web MVC 의 Controller 로 구현된다.

<figure><img src="https://slid-users-assets-v1-seoul.s3.ap-northeast-2.amazonaws.com/public/capture_images/8b26df16ff1b433996e1348abe71c5fc/276e90a7-5126-41b0-831d-e936cdb3a376.png" alt=""><figcaption></figcaption></figure>

사실은 모두 기능들이다.

UUID 를 사용해서 코드를 수정해보자

UUID 는 자바에서 기본적으로 제공을 해준다.

<figure><img src="https://slid-users-assets-v1-seoul.s3.ap-northeast-2.amazonaws.com/public/capture_images/8b26df16ff1b433996e1348abe71c5fc/139bf35a-ad71-4a2e-832b-e0ebd8b918e1.png" alt=""><figcaption></figcaption></figure>

그리고 서버를 실행시킨다.

http POST localhost:8080/posts title="title" content="content"

만약에 하이픈이 변경하고싶다고하면

<figure><img src="https://slid-users-assets-v1-seoul.s3.ap-northeast-2.amazonaws.com/public/capture_images/8b26df16ff1b433996e1348abe71c5fc/648a094f-7d90-4b4c-97ce-cb738a5971ac.png" alt=""><figcaption></figcaption></figure>

이렇게 변경해주면 된다

UUID에도 단점은 존재한다.

sorting 이 안된다.

그래서 UUID 에도 sorting 하고싶을땐 ULID 를 사용하면된다.

이것도 자바에서 사용할 수 있는 라이브러리가 존재한다.

<figure><img src="https://slid-users-assets-v1-seoul.s3.ap-northeast-2.amazonaws.com/public/capture_images/8b26df16ff1b433996e1348abe71c5fc/73016a39-f446-446a-937c-33d63be0c8a3.png" alt=""><figcaption></figcaption></figure>



<figure><img src="https://slid-users-assets-v1-seoul.s3.ap-northeast-2.amazonaws.com/public/capture_images/8b26df16ff1b433996e1348abe71c5fc/0fccb6f6-0e57-4c2f-8f5f-266f2b28b446.png" alt=""><figcaption></figcaption></figure>





<figure><img src="https://slid-users-assets-v1-seoul.s3.ap-northeast-2.amazonaws.com/public/capture_images/8b26df16ff1b433996e1348abe71c5fc/e7b74130-79f3-47bb-93bf-b9612916f659.png" alt=""><figcaption></figcaption></figure>

이제 코드를 수정해본다.

<figure><img src="https://slid-users-assets-v1-seoul.s3.ap-northeast-2.amazonaws.com/public/capture_images/8b26df16ff1b433996e1348abe71c5fc/333c3b21-9cd5-40a6-8857-b96a159dfcdc.png" alt=""><figcaption></figcaption></figure>

위처럼 코드수정하게 되면 앞자리가 크게 변경되지않습니다.

sorting 이 되는것입니다.

<figure><img src="https://slid-users-assets-v1-seoul.s3.ap-northeast-2.amazonaws.com/public/capture_images/8b26df16ff1b433996e1348abe71c5fc/c4b96373-4df4-44c5-9297-1ef3a867b148.png" alt=""><figcaption></figcaption></figure>

말고도 시간순으로 정렬하는것도 있습니다.

<figure><img src="https://slid-users-assets-v1-seoul.s3.ap-northeast-2.amazonaws.com/public/capture_images/8b26df16ff1b433996e1348abe71c5fc/c4449465-f141-4b35-9788-8bbec3d59604.png" alt=""><figcaption></figcaption></figure>

마찬가지로 의존성을 추가해서 사용하면 됩니다.

<figure><img src="https://slid-users-assets-v1-seoul.s3.ap-northeast-2.amazonaws.com/public/capture_images/8b26df16ff1b433996e1348abe71c5fc/b3fc8448-ddb7-487b-b389-bfb3b43f5ff4.png" alt=""><figcaption></figcaption></figure>



<figure><img src="https://slid-users-assets-v1-seoul.s3.ap-northeast-2.amazonaws.com/public/capture_images/8b26df16ff1b433996e1348abe71c5fc/b77d5fb8-48a1-4625-b5d8-b71a23ed3c1e.png" alt=""><figcaption></figcaption></figure>



<figure><img src="https://slid-users-assets-v1-seoul.s3.ap-northeast-2.amazonaws.com/public/capture_images/8b26df16ff1b433996e1348abe71c5fc/c49ab1d3-5e59-40e4-bfa6-4efc9874fb42.png" alt=""><figcaption></figcaption></figure>

## PostService

<figure><img src="https://slid-users-assets-v1-seoul.s3.ap-northeast-2.amazonaws.com/public/capture_images/8b26df16ff1b433996e1348abe71c5fc/3f2a87be-8852-4efc-a149-36cff267621a.png" alt=""><figcaption></figcaption></figure>



<figure><img src="https://slid-users-assets-v1-seoul.s3.ap-northeast-2.amazonaws.com/public/capture_images/8b26df16ff1b433996e1348abe71c5fc/c6333e09-69c9-4ebf-80bc-bcdb8256a97f.png" alt=""><figcaption></figcaption></figure>





<figure><img src="https://slid-users-assets-v1-seoul.s3.ap-northeast-2.amazonaws.com/public/capture_images/8b26df16ff1b433996e1348abe71c5fc/54951d6d-09e2-4731-b0a2-3d073f7e48aa.png" alt=""><figcaption></figcaption></figure>

이런식으로 코드 수정이 가능하다.

나머지도 비슷하게 수정하면 된다.

<figure><img src="https://slid-users-assets-v1-seoul.s3.ap-northeast-2.amazonaws.com/public/capture_images/8b26df16ff1b433996e1348abe71c5fc/d0b9020c-d0b4-464c-b98c-40ec0bbb4a86.png" alt=""><figcaption></figcaption></figure>

Create 도 PostService 에 추가를 해줍니다.

그리고 Controller 에도 코드를 수정하면 됩니다.

<figure><img src="https://slid-users-assets-v1-seoul.s3.ap-northeast-2.amazonaws.com/public/capture_images/8b26df16ff1b433996e1348abe71c5fc/2f20c1c9-425e-430d-8f71-82099b4a1cdf.png" alt=""><figcaption></figcaption></figure>

update 도 해줍니다.

update 하기전에 먼저 데이터를 찾아야합니다.

데이터를 찾는 코드는 다른곳에서도 자주 사용합니다.

이럴때 자주사용하는 코드를 메서드로 변경해서 따로 빼주는것이 좋습니다.

드래그를 해서 마우스 오른쪽 버튼을 눌러줍니다.

그리고 Refactor → Extract Method 를 클릭해줍니다.

<figure><img src="https://slid-users-assets-v1-seoul.s3.ap-northeast-2.amazonaws.com/public/capture_images/8b26df16ff1b433996e1348abe71c5fc/69dc23db-71e1-490e-ad40-76c0b8b95363.png" alt=""><figcaption></figcaption></figure>

아니면 단축키 command + m 키를 눌러서 빼줘도 됩니다.

<figure><img src="https://slid-users-assets-v1-seoul.s3.ap-northeast-2.amazonaws.com/public/capture_images/8b26df16ff1b433996e1348abe71c5fc/41d88662-8423-49e5-826b-2c4ef5a8f872.png" alt=""><figcaption></figcaption></figure>

위의 리팩토링 기법은 자주 사용하게 될것입니다.

<figure><img src="https://slid-users-assets-v1-seoul.s3.ap-northeast-2.amazonaws.com/public/capture_images/8b26df16ff1b433996e1348abe71c5fc/b6d4f528-643f-4597-9891-d0ad84b51871.png" alt=""><figcaption></figcaption></figure>



<figure><img src="https://slid-users-assets-v1-seoul.s3.ap-northeast-2.amazonaws.com/public/capture_images/8b26df16ff1b433996e1348abe71c5fc/9ff4277c-8c77-4cd4-b87e-8d893c5d5b75.png" alt=""><figcaption></figcaption></figure>

이렇게 해주게 되면 update 도 끝나게 됩니다.

delete 도 수정을 해줍니다.

<figure><img src="https://slid-users-assets-v1-seoul.s3.ap-northeast-2.amazonaws.com/public/capture_images/8b26df16ff1b433996e1348abe71c5fc/4370659d-7165-4eaa-ac76-1187a0ce790c.png" alt=""><figcaption></figcaption></figure>

기능 부분을 위와같이 빼주는것입니다.

서로 아무런 상관없이 굴러가게 됩니다.

최근에는 service 를 application 으로 많이 사용하기도 합니다.

<figure><img src="https://slid-users-assets-v1-seoul.s3.ap-northeast-2.amazonaws.com/public/capture_images/8b26df16ff1b433996e1348abe71c5fc/ba3614f8-7fcf-4954-8dc3-9d42935c18a7.png" alt=""><figcaption></figcaption></figure>

이거는 회사마다 조직마다 다릅니다.

```
Service
각 기능을 개별 메서드로 분리하고, 이를 모아서 PostService 클래스로 모아주고, 다시 application 패키지로
옮긴다.
관심사의 분리에 따라서 코드도 분리. 코드를 어떻게 배치하느냐 = 설계 설계를 개선 = 리팩터링|
```



* 관심사의 분리
  * 커다란 프로그램은 유지보수가 어렵다. 인간의 한계 + 공간의 한계, 유지보수가 가능하도록 적절하게 나누고, 그룹화 해야한다. 파일 시스템의 폴더나 Java의 패키지 등이 이를 위해 존재한다.\
    인간의 한계를 알고 효율적으로 활용하자. !
  * 관심사의 분리에 따라서 코드분리 , 코드를 어떻게 배치하느냐 = 설계, 설계 개선
* 응집도\
  한 클래스나 모듈 내부의 요소들이 서로 얼마나 밀접하게 관련되어 있는지를 나타낸다.\
  응집도가 높을수록 클래스나 모듈은 하나의 명확한 목적이나 기능에 집중한다.
* 결합도\
  서로 다른 클래스나 모듈 간의 의존 관계의 정도를 나타낸다. 결합도가 낮을수록 각 클래스나 모듈은 서로 독립적이며, 변경에 대한 영향이 적어집니다.
  * DI 와 IOC는 객체 간의 결합도를 낮춥니다. 객체는 필요한 의존성을 외부에서 주입받기 때문에 , 특정 구현에 강하게 결합되지 않습니다. 이는 코드의 유연성을 높이고 , 테스트와 유지보수를 용이하게 합니다.
  * DI 와 IOC 를 사용하게 되면 설계가 조금더 깔끔하게 됩니다.\
    각 클래스는 자신의 역할에 집중할 수 있게되고, 외부 의존성에 대해서는 걱정할 필요가 없어지게 됩니다.
* Layered Atchitecture 계층화 아키텍쳐
* UUID
  * 소프트웨어 개발에서 고유성을 보장하는데 사용되는 128비트의 숫자이다. 이 식별자는 전 세계적으로 고유하며 , 중복될 확률이 극히 낮다.
  * `String id = UUID.randomUUID().toString();`
* ULID
  * Sortable 한 UUID\
    ![](<../.gitbook/assets/스크린샷 2023-11-19 오전 11.56.20.png>)
  * UUID 의 장점을 유지하면서 몇가지 추가적인 이점을 제공한다.
    * 정렬: ULID 는 시간 기반으로 생성되며 , 이로 인해 생성된 순서대로 정렬할 수 있습니다.
    * 고유성: ULID 는 UUID 와 마찬가지로 전 세계적으로 고유한 값을 생성할 수 있다.
    * 128비트 크기: ULID 는 128비트 크기를 가지며, 이는 UUID와 동일하다. 이로 인해 기존의 UUID 시스템과 호환성을 유지할 수 있습니다.
  * `String id = UlidCreator.getUlid().toString();`
