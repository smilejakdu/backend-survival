# Jackson ObjectMapper



## 강의 내용

## Jackson ObjectMapper

<figure><img src="https://slid-users-assets-v1-seoul.s3.ap-northeast-2.amazonaws.com/public/capture_images/4c90c8fccf96409a9e41861adf99c686/a7e1127e-4b94-4fc9-a465-3b84281ce5b8.png" alt=""><figcaption></figcaption></figure>

지난 번에 우리가 작성한 프로젝트를 open 한다.

<figure><img src="https://slid-users-assets-v1-seoul.s3.ap-northeast-2.amazonaws.com/public/capture_images/4c90c8fccf96409a9e41861adf99c686/7ada5886-a9a1-441b-8f58-dd088218406a.png" alt=""><figcaption></figcaption></figure>

혹시나 exceptions 패키지를 만들지 않았다면 exceptions 패키지를 만들어주고,

PostNotFound 파일을 생성한다.



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

ObjectMapper 가 뭘까 ??



`Jackson ObjectMapper` 는 자바에서 널리 사용되는 라이브러리 중 하나로, JSON 데이터를 자바 객체로 변환하거나 자바 객체를 JSON으로 변환하는 데 사용됩니다. 이 기능은 JSON 파싱과 데이터 바인딩으로 불리며, 다양한 데이터 처리 작업에서 매우 유용합니다. ObjectMapper의 주요 기능과 특징은 다음과 같습니다:

1. **데이터 바인딩**: ObjectMapper는 JSON 문자열을 자바 객체로 변환하거나, 반대로 자바 객체를 JSON으로 변환할 수 있습니다. 이것을 데이터 바인딩이라고 하며, 간단한 API 호출을 통해 수행됩니다.
2. **주석(Annotation) 사용**: 자바 클래스에 주석을 추가함으로써, ObjectMapper는 JSON과 객체 간의 매핑을 더 세밀하게 제어할 수 있습니다. 예를 들어, `@JsonProperty` 주석은 JSON 속성과 자바 필드 간의 매핑을 정의합니다.
3. **유연성**: ObjectMapper는 다양한 유형의 JSON 데이터와 자바 객체를 처리할 수 있는 유연성을 제공합니다. 이는 컬렉션, 배열, 제네릭 타입, 사용자 정의 객체 등 다양한 형태의 데이터를 쉽게 처리할 수 있게 해줍니다.
4. **스트리밍 API**: Jackson은 스트리밍 API도 제공하여, 대용량 JSON 데이터를 메모리에 모두 로드하지 않고도 처리할 수 있게 해줍니다. 이는 성능과 메모리 사용 측면에서 효율적입니다.
5. **확장성**: Jackson은 커스텀 직렬화 및 역직렬화 로직을 구현하여 확장할 수 있습니다. 이를 통해 복잡한 객체 구조나 특별한 요구 사항을 가진 데이터 처리가 가능합니다.
6. **성능**: Jackson은 빠른 처리 속도와 낮은 메모리 사용량으로 알려져 있으며, 대규모 애플리케이션에서도 효과적으로 사용됩니다.

Jackson ObjectMapper는 그 자체로 강력한 도구이며, 스프링 프레임워크와 같은 다른 자바 기반 프레임워크와 함께 사용될 때 더욱 강력한 성능을 발휘합니다. JSON 처리를 위한 주요 라이브러리 중 하나로, 현대 웹 애플리케이션 개발에서 중요한 역할을 합니다.



<figure><img src="https://slid-users-assets-v1-seoul.s3.ap-northeast-2.amazonaws.com/public/capture_images/4c90c8fccf96409a9e41861adf99c686/7dde5f6b-7bb5-4090-a824-8e1b75718d27.png" alt=""><figcaption></figcaption></figure>

<figure><img src="https://slid-users-assets-v1-seoul.s3.ap-northeast-2.amazonaws.com/public/capture_images/4c90c8fccf96409a9e41861adf99c686/28696de1-23ae-4b92-90b0-5f678c66d1c4.png" alt=""><figcaption></figcaption></figure>

<figure><img src="https://slid-users-assets-v1-seoul.s3.ap-northeast-2.amazonaws.com/public/capture_images/4c90c8fccf96409a9e41861adf99c686/ce36b347-134d-42f3-b9a4-45244c8b081c.png" alt=""><figcaption></figcaption></figure>

이후 objectMapper 를 사용해보자 .

<figure><img src="https://slid-users-assets-v1-seoul.s3.ap-northeast-2.amazonaws.com/public/capture_images/4c90c8fccf96409a9e41861adf99c686/f30d9479-6876-4fef-b1d3-9d01779e3c16.png" alt=""><figcaption></figcaption></figure>

이후에 빌드 실행을 해본다.

curl localhost:8080/posts/1

<figure><img src="https://slid-users-assets-v1-seoul.s3.ap-northeast-2.amazonaws.com/public/capture_images/4c90c8fccf96409a9e41861adf99c686/3a7718f3-192d-478d-996d-7d85bcb24661.png" alt=""><figcaption></figcaption></figure>

<figure><img src="https://slid-users-assets-v1-seoul.s3.ap-northeast-2.amazonaws.com/public/capture_images/4c90c8fccf96409a9e41861adf99c686/4dac306b-df95-4b94-abf6-9ad34447deab.png" alt=""><figcaption></figcaption></figure>

<figure><img src="https://slid-users-assets-v1-seoul.s3.ap-northeast-2.amazonaws.com/public/capture_images/4c90c8fccf96409a9e41861adf99c686/feb3b75a-72b4-4472-8e85-15d400adf856.png" alt=""><figcaption></figcaption></figure>

<figure><img src="https://slid-users-assets-v1-seoul.s3.ap-northeast-2.amazonaws.com/public/capture_images/4c90c8fccf96409a9e41861adf99c686/503a5e2f-815e-4c27-89cd-e8243d173dc2.png" alt=""><figcaption></figcaption></figure>



<figure><img src="https://slid-users-assets-v1-seoul.s3.ap-northeast-2.amazonaws.com/public/capture_images/4c90c8fccf96409a9e41861adf99c686/1e6651bd-5e54-4bf6-b41e-06d0080deb1d.png" alt=""><figcaption></figcaption></figure>



<figure><img src="https://slid-users-assets-v1-seoul.s3.ap-northeast-2.amazonaws.com/public/capture_images/4c90c8fccf96409a9e41861adf99c686/61bde54f-197b-431d-86bc-846b9f561697.png" alt=""><figcaption></figcaption></figure>

로 다시 수정한다.

Patch 도 수정하도록 한다.

![https://slid-users-assets-v1-seoul.s3.ap-northeast-2.amazonaws.com/public/capture\_images/4c90c8fccf96409a9e41861adf99c686/462305e2-5a31-47c4-b390-61118df852c2.png](https://slid-users-assets-v1-seoul.s3.ap-northeast-2.amazonaws.com/public/capture\_images/4c90c8fccf96409a9e41861adf99c686/462305e2-5a31-47c4-b390-61118df852c2.png)

postDto 에 setId 를 만들어준다.

<figure><img src="https://slid-users-assets-v1-seoul.s3.ap-northeast-2.amazonaws.com/public/capture_images/4c90c8fccf96409a9e41861adf99c686/e994eac2-5e4d-4251-984a-16321eb478ac.png" alt=""><figcaption></figcaption></figure>



<figure><img src="https://slid-users-assets-v1-seoul.s3.ap-northeast-2.amazonaws.com/public/capture_images/4c90c8fccf96409a9e41861adf99c686/f189728f-8768-448c-9a9f-ae7414a4ea93.png" alt=""><figcaption></figcaption></figure>

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

