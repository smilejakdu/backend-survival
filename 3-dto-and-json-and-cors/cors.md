# CORS



## CORS 란

CORS (Cross-Origin Resource Sharing)는 웹 페이지에서 실행되는 코드가 다른 도메인의 리소스에 액세스할 수 있도록 하는 보안 메커니즘입니다. 웹 보안의 중요한 부분인 동일 출처 정책(Same-Origin Policy)은 기본적으로 한 출처(origin)에서 로드된 웹 페이지가 다른 출처의 리소스와 상호 작용하는 것을 제한합니다. CORS는 이러한 제한을 안전한 방식으로 완화하는 방법을 제공합니다.

#### 동일 출처 정책 (Same-Origin Policy)

* **목적**: 웹 페이지가 악의적인 스크립트를 포함하여 사용자의 데이터를 도용하거나 조작하는 것을 방지합니다.
* **정의**: 출처는 프로토콜, 호스트(도메인), 포트의 조합으로 정의됩니다. 예를 들어, `https://example.com` 페이지는 `https://api.example.com` 또는 `http://example.com` (다른 프로토콜)에서 로드된 리소스에 기본적으로 액세스할 수 없습니다.

#### CORS 작동 방식

1. **단순 요청 (Simple Requests)**:
   * **조건**: GET, HEAD, POST 메소드와 일부 HTTP 헤더만 사용하는 요청.
   * **프로세스**: 브라우저는 자동으로 `Origin` 헤더를 요청에 추가합니다. 서버는 이를 확인하고, `Access-Control-Allow-Origin` 헤더를 응답에 포함하여 해당 출처의 액세스를 허용할지 결정합니다.
2. **사전 요청 (Preflight Requests)**:
   * **조건**: PUT, DELETE 또는 사용자 정의 헤더를 사용하는 요청 등, 단순 요청에 해당하지 않는 경우.
   * **프로세스**: 브라우저는 실제 요청을 보내기 전에 `OPTIONS` 메소드를 사용한 사전 요청을 보냅니다. 이 요청은 서버가 요청을 수락할지 결정할 수 있도록 필요한 정보를 포함합니다. 서버는 `Access-Control-Allow-Origin` 및 다른 CORS 관련 헤더들로 응답합니다.
3. **응답 헤더**:
   * 주요 헤더들: `Access-Control-Allow-Origin`, `Access-Control-Allow-Methods`, `Access-Control-Allow-Headers`.

#### CORS의 중요성

* **보안 유지**: CORS는 보안을 유지하면서도 다른 출처의 리소스에 대한 액세스를 가능하게 합니다.
* **API 사용 용이성**: 다른 출처에서 호스팅되는 API에 대한 액세스를 허용함으로써, 개발자는 다양한 웹 서비스와 상호 작용할 수 있습니다.
* **유연성**: 서버 측에서 CORS 정책을 구성함으로써, 어떤 출처에서의 액세스를 허용할지 세밀하게 제어할 수 있습니다.

CORS는 웹 개발에서 핵심적인 부분으로, 현대 인터넷의 연결성과 상호 운용성에 중요한 역할을 합니다. 개발자는 CORS를 적절히 이해하고 구현함으로써 보안을 유지하면서도 다양한 웹 리소스와 효율적으로 상호 작용할 수 있습니다.

## 강의 내용

<figure><img src="https://slid-users-assets-v1-seoul.s3.ap-northeast-2.amazonaws.com/public/capture_images/c8d1a914431d4213a148e1d2848490b0/7854c63b-ffc5-4cc1-ac8b-3efa86a74aac.png" alt=""><figcaption></figcaption></figure>

<figure><img src="https://slid-users-assets-v1-seoul.s3.ap-northeast-2.amazonaws.com/public/capture_images/c8d1a914431d4213a148e1d2848490b0/d7f0e61c-536d-4029-b682-10f2a8ab1570.png" alt=""><figcaption></figcaption></figure>

눌러봐도 response 들어와야하는데 아무것도 안들어와있다.

데이터가 전혀 오지않았다.

<figure><img src="https://slid-users-assets-v1-seoul.s3.ap-northeast-2.amazonaws.com/public/capture_images/c8d1a914431d4213a148e1d2848490b0/986d3887-fba6-4f2a-8b89-af0f3b4395fa.png" alt=""><figcaption></figcaption></figure>

CORS 에러가 발생함

웹 브라우저가 처리하는 보안 정책이다.

Same-Origin Policy

참고: https://github.com/ahastucio/til/blob/main/http/20201205-cors.md

https://developer.mozilla.org/ko/docs/Web/Security/Same-origin\_policy

웹 브라우저가 처리하는 보안 정책. 얻으려는 리소스의 출처(호스트) 가 현재 페이지와 다르면 접근할 수 없게 하는 보안 정책. 출처에는 포트까지 포함된다는 점에 주의.

분명 요청을 했고 response 도 왔다.

<figure><img src="https://slid-users-assets-v1-seoul.s3.ap-northeast-2.amazonaws.com/public/capture_images/c8d1a914431d4213a148e1d2848490b0/055b4e26-d3ce-4f48-b154-d6961f30bd1a.png" alt=""><figcaption></figcaption></figure>

response 를 얻어왔다. 하지만 웹브라우저에서 보안상 문제가 될 수 있다고 말하는거다.

<figure><img src="https://slid-users-assets-v1-seoul.s3.ap-northeast-2.amazonaws.com/public/capture_images/c8d1a914431d4213a148e1d2848490b0/3141413f-b701-406e-a3ae-4cd08b182bdd.png" alt=""><figcaption></figcaption></figure>

출처가 Origin 이라고 보면 된다.

출처에는 port 까지 포함된다.

Host: http://localhost:8080 → Backend REST API

Origin: http://localhost:3000 → Frontend

그래서 Cors 설정을 해줘야한다.

Backend 즉 REST API 의 응답 헤더에 Access-Control-Allow-Origin 속성을 포함시키면 됨.

서버 쪽에서 여기에서 요청한 거라면 괜찮아요 라고 알려주는 방식.

요청 헤더의 Origin 속성을 참고할 것

* 웹 페이지: https://ahastudio.com
* API 서버 : https://api.ahastudio.com

HTTP/1.1 200 OK

<figure><img src="https://slid-users-assets-v1-seoul.s3.ap-northeast-2.amazonaws.com/public/capture_images/c8d1a914431d4213a148e1d2848490b0/fde82620-6fec-4a14-ab8f-4e13be939037.png" alt=""><figcaption></figcaption></figure>

위와 같이 수정하고 나서 다시 새로고침을 해준다.

<figure><img src="https://slid-users-assets-v1-seoul.s3.ap-northeast-2.amazonaws.com/public/capture_images/c8d1a914431d4213a148e1d2848490b0/fe456ac8-fae4-4ec7-999b-c0272e14e7ed.png" alt=""><figcaption></figcaption></figure>



<figure><img src="https://slid-users-assets-v1-seoul.s3.ap-northeast-2.amazonaws.com/public/capture_images/c8d1a914431d4213a148e1d2848490b0/0e19e903-5d7a-449e-90dd-98148b1499ef.png" alt=""><figcaption></figcaption></figure>

잘 뜨는것을 확인 할 수 있습니다.

만약에 Origin 과 무관하게 모든 요청을 허용할 거면 그냥 "\*" 로 잡아주면 된다.

하지만 추천하지 않는다.

<figure><img src="https://slid-users-assets-v1-seoul.s3.ap-northeast-2.amazonaws.com/public/capture_images/c8d1a914431d4213a148e1d2848490b0/63e2a706-bc53-48a6-ae48-faddb85218f8.png" alt=""><figcaption></figcaption></figure>

이렇게하면 뭘해도 상관없다.

말고 더 깔끔하게 하는 방법이 존재하는데 @CrossOrigin 으로 하는 방법이 존재한다.

```java
@CrossOrigin
https://docs.spring.io/spring-framework/docs/current/javadoc-api/org/springframework/web/bind/an
notation/CrossOrigin.html

```

```java
@CrossOrigin("http://localhost:3000")
@PostMapping
@ResponseStatus (HttpStatus.CREATED)
public PostDto create (@RequestBody PostDto postDto) {
    postDto.setId("1004");
    return postDto;
}
```

이런식으로 변경해주도록 한다.

하지만 그러면 요청되는 Controller 마다 어노테이션 CrossOrigin 을 넣어줘야할까?

<figure><img src="https://slid-users-assets-v1-seoul.s3.ap-northeast-2.amazonaws.com/public/capture_images/c8d1a914431d4213a148e1d2848490b0/77f10d5e-ffb2-421e-9528-3187d4101c63.png" alt=""><figcaption></figcaption></figure>

이렇게 하더라도 해당하는 컨트롤러만 CrossOrigin 설정을 한것이지 전반적으로 설정은 되지 않았다.

```java
@DeleteMapping ("/{id}")
public PostDto delete (@PathVariable String id) {
         PostDto postDto = postDtos.stream()
                     .filter(i->i.getId().equals(id))
                     .findFirst()
                     .get();
         postDtos.remove(postDto);
         return postDto;
}

```

삭제코드를 수정한다.

<figure><img src="https://slid-users-assets-v1-seoul.s3.ap-northeast-2.amazonaws.com/public/capture_images/c8d1a914431d4213a148e1d2848490b0/63b86537-8a61-4afd-a885-725c8f975873.png" alt=""><figcaption></figcaption></figure>

@SpringBootApplication 어노테이션이 있는 main 클래스로 간다.



<figure><img src="https://slid-users-assets-v1-seoul.s3.ap-northeast-2.amazonaws.com/public/capture_images/c8d1a914431d4213a148e1d2848490b0/315c14a5-2c78-4d67-b99d-008e371e722a.png" alt=""><figcaption></figcaption></figure>

Methods 를 추가할수도 있다.

<figure><img src="https://slid-users-assets-v1-seoul.s3.ap-northeast-2.amazonaws.com/public/capture_images/c8d1a914431d4213a148e1d2848490b0/6591489c-cacf-4416-972d-348aa01e0e08.png" alt=""><figcaption></figcaption></figure>

```java
@Bean
public WebMvcConfigurer webMvcConfigurer() {
    return new WebMvcConfigureer() {
        @Override
        public void addCorsMappings(CorsRegistry registry) {
            registry
                .addMapping("/**")
                .allowedMethods("GET","POST","PATCH","DELETE","OPTIONS")
                .allowedOrigins("http://localhost:3000");
        }
    }
}
```



### ✅ 동일 출처 정책

* Protocol + host + port 3가지가 같으면 동일 출처라고 한다.
*

    <figure><img src="../.gitbook/assets/스크린샷 2023-11-19 오전 12.23.12.png" alt=""><figcaption></figcaption></figure>



### ✅ 다른 출처 정책

그렇다면 다른 출처 정책은 뭘까 ?

request 보내는 client 와 request 를 받는 서버가 같은 출처에 있으면 동일  출처,

서로 다른 서버에 있으면 다른 출처 요청 입니다.



## ✅ JSONP

JSONP 는 cors 가 활성화 되기 이전의 데이터 요청방법니다.

JSONP 도 다른 도메인으로부터 데이터를 가져오기 위해 사용하는 방법이다.

## ✅ Access-Control-Allow-Origin

{% embed url="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Access-Control-Allow-Origin" %}

`Access-Control-Allow-Origin` 헤더는 서버가 특정 출처, 또는 모든 출처에서 자신의 리소스에 접근하는 것을 허용하도록 설정할 수 있게 해줍니다.

이 헤더는 서버의 응답에 포함되어야 합니다

* 특정 출처 허용: 만약 `https://example.com` 이 `https://api.server.com` 의 데이터에 접근하려면\
  `api.server.com` 서버는 응답에 다음과 같은 헤더를 포함해야 한다.\
  Access-Control-Allow-Origin: https://example.com
* 모든 출처 허용: 모든 출처에서의 접근을 허용하려면, 서버는 응답에 다음과 같은 헤더를 포함할 수 있습니다.

## ✅ CrossOrigin`@CrossOrigin`&#x20;



{% embed url="https://developer.mozilla.org/ko/docs/Web/HTML/Attributes/crossorigin" %}

모든 출처를 허용하는 것(`@CrossOrigin` 또는 `@CrossOrigin(origins = "*")`)은 보안상 위험할 수 있으므로, 필요한 경우에만 사용하고 가능한 한 제한적으로 설정하는 것이 좋습니다.\
CORS 정책은 브라우저 기반 클라이언트에만 적용됩니다. 서버 간 통신이나 브라우저가 아닌 클라이언트에서는 이 정책이 적용되지 않습니다.
