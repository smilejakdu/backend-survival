# Jackson ObjectMapper



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

