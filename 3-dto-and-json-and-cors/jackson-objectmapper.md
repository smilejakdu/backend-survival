# Jackson ObjectMapper



## 강의 내용

## Jackson ObjectMapper

<figure><img src="https://slid-users-assets-v1-seoul.s3.ap-northeast-2.amazonaws.com/public/capture_images/4c90c8fccf96409a9e41861adf99c686/a7e1127e-4b94-4fc9-a465-3b84281ce5b8.png" alt=""><figcaption></figcaption></figure>

지난 번에 우리가 작성한 프로젝트를 open 한다.

<figure><img src="https://slid-users-assets-v1-seoul.s3.ap-northeast-2.amazonaws.com/public/capture_images/4c90c8fccf96409a9e41861adf99c686/7ada5886-a9a1-441b-8f58-dd088218406a.png" alt=""><figcaption></figcaption></figure>

dtos 패키지를 추가한다.

<figure><img src="https://slid-users-assets-v1-seoul.s3.ap-northeast-2.amazonaws.com/public/capture_images/4c90c8fccf96409a9e41861adf99c686/3b526b51-0cf0-441b-b1e5-3717a03d4ba9.png" alt=""><figcaption></figcaption></figure>

dtos 를 여기에 만들어도 되고 아니면 controllers 안에다가 dtos 를 만들어서 해도 된다.

PostDto 를 생성하자.

<figure><img src="https://slid-users-assets-v1-seoul.s3.ap-northeast-2.amazonaws.com/public/capture_images/4c90c8fccf96409a9e41861adf99c686/73e8d785-8878-499f-ad43-d44fd4ab8947.png" alt=""><figcaption></figcaption></figure>

그리고 컨트롤 + enter 를 누르게 되면 generate 가 나오게 된다.

<figure><img src="https://slid-users-assets-v1-seoul.s3.ap-northeast-2.amazonaws.com/public/capture_images/4c90c8fccf96409a9e41861adf99c686/7269a4fe-b1dc-4007-82ed-6997b396929f.png" alt=""><figcaption></figcaption></figure>

이렇게해서 Getter 와 Setter 를 간단히 생성할 수 있다.

물론 공부를 하셨다면 오너테이션으로 getter 와 setter 를 나중에 작성하지 않겠지만 우선 작성하도록 하자 .

<figure><img src="https://slid-users-assets-v1-seoul.s3.ap-northeast-2.amazonaws.com/public/capture_images/4c90c8fccf96409a9e41861adf99c686/3708e152-7977-4441-a7f1-0d23361d93e4.png" alt=""><figcaption></figcaption></figure>

이제 PostController 로 가서 ObjectMapper 를 불러와준다.

<figure><img src="https://slid-users-assets-v1-seoul.s3.ap-northeast-2.amazonaws.com/public/capture_images/4c90c8fccf96409a9e41861adf99c686/5599956f-82dd-40f3-82a7-cba8f5ef2b24.png" alt=""><figcaption></figcaption></figure>

<figure><img src="https://slid-users-assets-v1-seoul.s3.ap-northeast-2.amazonaws.com/public/capture_images/4c90c8fccf96409a9e41861adf99c686/9679d5ad-0b1f-4162-a0f0-9e229c12af12.png" alt=""><figcaption></figcaption></figure>

ObjectMapper 가 뭐야 ??

![https://slid-users-assets-v1-seoul.s3.ap-northeast-2.amazonaws.com/public/capture\_images/4c90c8fccf96409a9e41861adf99c686/7dde5f6b-7bb5-4090-a824-8e1b75718d27.png](https://slid-users-assets-v1-seoul.s3.ap-northeast-2.amazonaws.com/public/capture\_images/4c90c8fccf96409a9e41861adf99c686/7dde5f6b-7bb5-4090-a824-8e1b75718d27.png)![https://slid-users-assets-v1-seoul.s3.ap-northeast-2.amazonaws.com/public/capture\_images/4c90c8fccf96409a9e41861adf99c686/28696de1-23ae-4b92-90b0-5f678c66d1c4.png](https://slid-users-assets-v1-seoul.s3.ap-northeast-2.amazonaws.com/public/capture\_images/4c90c8fccf96409a9e41861adf99c686/28696de1-23ae-4b92-90b0-5f678c66d1c4.png)![https://slid-users-assets-v1-seoul.s3.ap-northeast-2.amazonaws.com/public/capture\_images/4c90c8fccf96409a9e41861adf99c686/ce36b347-134d-42f3-b9a4-45244c8b081c.png](https://slid-users-assets-v1-seoul.s3.ap-northeast-2.amazonaws.com/public/capture\_images/4c90c8fccf96409a9e41861adf99c686/ce36b347-134d-42f3-b9a4-45244c8b081c.png)

이후 objectMapper 를 사용해보자 .

![https://slid-users-assets-v1-seoul.s3.ap-northeast-2.amazonaws.com/public/capture\_images/4c90c8fccf96409a9e41861adf99c686/f30d9479-6876-4fef-b1d3-9d01779e3c16.png](https://slid-users-assets-v1-seoul.s3.ap-northeast-2.amazonaws.com/public/capture\_images/4c90c8fccf96409a9e41861adf99c686/f30d9479-6876-4fef-b1d3-9d01779e3c16.png)

이후에 빌드 실행을 해본다.

curl localhost:8080/posts/1

![https://slid-users-assets-v1-seoul.s3.ap-northeast-2.amazonaws.com/public/capture\_images/4c90c8fccf96409a9e41861adf99c686/3a7718f3-192d-478d-996d-7d85bcb24661.png](https://slid-users-assets-v1-seoul.s3.ap-northeast-2.amazonaws.com/public/capture\_images/4c90c8fccf96409a9e41861adf99c686/3a7718f3-192d-478d-996d-7d85bcb24661.png)![https://slid-users-assets-v1-seoul.s3.ap-northeast-2.amazonaws.com/public/capture\_images/4c90c8fccf96409a9e41861adf99c686/4dac306b-df95-4b94-abf6-9ad34447deab.png](https://slid-users-assets-v1-seoul.s3.ap-northeast-2.amazonaws.com/public/capture\_images/4c90c8fccf96409a9e41861adf99c686/4dac306b-df95-4b94-abf6-9ad34447deab.png)![https://slid-users-assets-v1-seoul.s3.ap-northeast-2.amazonaws.com/public/capture\_images/4c90c8fccf96409a9e41861adf99c686/feb3b75a-72b4-4472-8e85-15d400adf856.png](https://slid-users-assets-v1-seoul.s3.ap-northeast-2.amazonaws.com/public/capture\_images/4c90c8fccf96409a9e41861adf99c686/feb3b75a-72b4-4472-8e85-15d400adf856.png)![https://slid-users-assets-v1-seoul.s3.ap-northeast-2.amazonaws.com/public/capture\_images/4c90c8fccf96409a9e41861adf99c686/503a5e2f-815e-4c27-89cd-e8243d173dc2.png](https://slid-users-assets-v1-seoul.s3.ap-northeast-2.amazonaws.com/public/capture\_images/4c90c8fccf96409a9e41861adf99c686/503a5e2f-815e-4c27-89cd-e8243d173dc2.png)![https://slid-users-assets-v1-seoul.s3.ap-northeast-2.amazonaws.com/public/capture\_images/4c90c8fccf96409a9e41861adf99c686/1e6651bd-5e54-4bf6-b41e-06d0080deb1d.png](https://slid-users-assets-v1-seoul.s3.ap-northeast-2.amazonaws.com/public/capture\_images/4c90c8fccf96409a9e41861adf99c686/1e6651bd-5e54-4bf6-b41e-06d0080deb1d.png)![https://slid-users-assets-v1-seoul.s3.ap-northeast-2.amazonaws.com/public/capture\_images/4c90c8fccf96409a9e41861adf99c686/61bde54f-197b-431d-86bc-846b9f561697.png](https://slid-users-assets-v1-seoul.s3.ap-northeast-2.amazonaws.com/public/capture\_images/4c90c8fccf96409a9e41861adf99c686/61bde54f-197b-431d-86bc-846b9f561697.png)

로 다시 수정한다.undefined

Patch 도 수정하도록 한다.

![https://slid-users-assets-v1-seoul.s3.ap-northeast-2.amazonaws.com/public/capture\_images/4c90c8fccf96409a9e41861adf99c686/462305e2-5a31-47c4-b390-61118df852c2.png](https://slid-users-assets-v1-seoul.s3.ap-northeast-2.amazonaws.com/public/capture\_images/4c90c8fccf96409a9e41861adf99c686/462305e2-5a31-47c4-b390-61118df852c2.png)

postDto 에 setId 를 만들어준다.

![https://slid-users-assets-v1-seoul.s3.ap-northeast-2.amazonaws.com/public/capture\_images/4c90c8fccf96409a9e41861adf99c686/e994eac2-5e4d-4251-984a-16321eb478ac.png](https://slid-users-assets-v1-seoul.s3.ap-northeast-2.amazonaws.com/public/capture\_images/4c90c8fccf96409a9e41861adf99c686/e994eac2-5e4d-4251-984a-16321eb478ac.png)![https://slid-users-assets-v1-seoul.s3.ap-northeast-2.amazonaws.com/public/capture\_images/4c90c8fccf96409a9e41861adf99c686/f189728f-8768-448c-9a9f-ae7414a4ea93.png](https://slid-users-assets-v1-seoul.s3.ap-northeast-2.amazonaws.com/public/capture\_images/4c90c8fccf96409a9e41861adf99c686/f189728f-8768-448c-9a9f-ae7414a4ea93.png)

알아서 json 으로 잘 빠지는것을 볼 수 있다.



`Jackson ObjectMapper` 를 사용해서 DTO 를 JSON (문자열) 으로 변환하거나, JSON(문자열) 을 DTO로 변환할 수 있다.



먼저, `DTO` 를 위한 `class` 를 만든다.

`JSON` 의 스키마를 작성한다는 느낌으로 만들면 된다.

필드보다는 `getter` 메서드의 이름을 따른다는 점에 주의하고,

만약 이름을 강제하고 싶다면 `@JsonProperty` 애너테이션을 사용하자.



`JSON 스키마`

```java
{
    "id" : "1234",
    "title" : "title",
    "content": "test"
}

```

Java 코드

```java
public class PostDto {
    private String id;
    private String title;
    private String content;
    
    public PostDto() {
    
    }
    
    public PostDto(String id, String title, String content) {
        this.id = id;
        this.title = title;
        this.content = content;
    }
    
```



<figure><img src="../.gitbook/assets/스크린샷 2023-11-18 오후 6.40.07.png" alt=""><figcaption></figcaption></figure>

<figure><img src="../.gitbook/assets/스크린샷 2023-11-18 오후 6.48.16.png" alt=""><figcaption></figcaption></figure>

이후에 실행하고나서 `curl localhost:8000/posts/1` 요청을 보내본다.

`writeValueAsString` 메서드에 어떤 인자값을 넣어도 모두 통과가 된다.

Jackson ObjectMapper 를 써서 DTO를 JSON 포맷의 String 으로 변환한다.

JsonProcessingException 예외가  Jackson 을 바로 쓸 수 있는 건 Spring Boot 가 Jackson 을 지원하기 때문, 변환 또한 Spring Boot  가 알아서 해주기 때문에 실제로는 아주 쉽고 자연스럽게 쓸 수 있다.



## 기본 기능

* 직렬화 : 자바 객체를 JSON 문자열로 변환합니다. 이 과정에서 객체의 공개 필드나 getter 메소드를 사용하여 객체의 상태를 JSON 으로 표현합니다.
* 역직렬화: JSON 문자열을 자바 객체로 변환합니다. 이 과정에서 JSON 의 키를 객체의 필드이름과 매핑하여 객체를 생성하고 초기화 합니다.
* 사용자 정의 직렬화 및 역직렬화 로직을 구현할 수 있습니다. 이를통해 복잡한 객체 구조나 특별한 JSON 형식을 처리할 수 있습니다.
* JsonIgnore 는 특정 필드를 JSON 에 포함하지 않도록 할 수 있습니다.

