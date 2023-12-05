# Spring Web MVC

<figure><img src="../.gitbook/assets/스크린샷 2023-12-05 오후 4.50.33.png" alt=""><figcaption></figcaption></figure>

프로젝트를 생성하고 프로젝트를 잘 생성했는지 테스트하기위해 설정한다.

cmd + , -> + 버튼을 클릭한다 -> gradle 를 추가하고 설정한다.

<figure><img src="../.gitbook/assets/스크린샷 2023-12-05 오후 4.52.43.png" alt=""><figcaption></figcaption></figure>



## 수업 내용

## Spring Web MVC로 구현

<figure><img src="https://slid-users-assets-v1-seoul.s3.ap-northeast-2.amazonaws.com/public/capture_images/f598ca893b8e4ebab5aa181708cc3124/31607771-a960-46fd-b350-c0135aefc9b4.png" alt=""><figcaption></figcaption></figure>

많이 넣지말고 롬북 Dev Tools , Spring Web 이렇게 3개만 넣어주도록 한다.

제대로 생성이 되었는지 test 설정을 해준다.

<figure><img src="https://slid-users-assets-v1-seoul.s3.ap-northeast-2.amazonaws.com/public/capture_images/f598ca893b8e4ebab5aa181708cc3124/1000473c-09ae-4282-97be-412c4e93ec2b.png" alt=""><figcaption></figcaption></figure>

Controller 를 만들어준다.

<figure><img src="https://slid-users-assets-v1-seoul.s3.ap-northeast-2.amazonaws.com/public/capture_images/f598ca893b8e4ebab5aa181708cc3124/c1e2e185-9665-4b43-bc90-f2bb99339a84.png" alt=""><figcaption></figcaption></figure>

post 를 먼저했고 CRUD 니까 나머지도해준다.

<figure><img src="https://slid-users-assets-v1-seoul.s3.ap-northeast-2.amazonaws.com/public/capture_images/f598ca893b8e4ebab5aa181708cc3124/272fb5f3-478c-480d-afc4-d816bfceab4a.png" alt=""><figcaption></figcaption></figure>

근데 1과 2의 차이를 조금 구분하고싶다.

<figure><img src="https://slid-users-assets-v1-seoul.s3.ap-northeast-2.amazonaws.com/public/capture_images/f598ca893b8e4ebab5aa181708cc3124/8f8f0c53-e831-4123-a76c-c329f6803c97.png" alt=""><figcaption></figcaption></figure>

에러 길이가 너무 길다. 이럴때 따로 설정할 수 있다.

<figure><img src="https://slid-users-assets-v1-seoul.s3.ap-northeast-2.amazonaws.com/public/capture_images/f598ca893b8e4ebab5aa181708cc3124/07cc6513-2f6d-44eb-bcdd-6f5e4d9eb716.png" alt=""><figcaption></figcaption></figure>

다 작성을 했으면 Post 를 해본다.

Post 에는 내용부분을 body 에 담아서 넘겨줘야한다.

<figure><img src="https://slid-users-assets-v1-seoul.s3.ap-northeast-2.amazonaws.com/public/capture_images/f598ca893b8e4ebab5aa181708cc3124/c056f819-22d4-4fb2-99ff-66897353389a.png" alt=""><figcaption></figcaption></figure>

이후 json 형식으로 return 하고 싶을때

<figure><img src="https://slid-users-assets-v1-seoul.s3.ap-northeast-2.amazonaws.com/public/capture_images/f598ca893b8e4ebab5aa181708cc3124/3ea5ca85-3c55-4618-a69e-935ff0a5961f.png" alt=""><figcaption></figcaption></figure>

원래는 이렇게 하면안되지만 우선은 이렇게하도록 하자

<figure><img src="https://slid-users-assets-v1-seoul.s3.ap-northeast-2.amazonaws.com/public/capture_images/f598ca893b8e4ebab5aa181708cc3124/1672571f-f9ed-4b47-8737-24bbcf4f795f.png" alt=""><figcaption></figcaption></figure>

수정하고 나서 다시 빌드하고 실행한다.

위의 url 주소를 보면 앞에 posts 가 중복해서 들어가고 있다.

<figure><img src="https://slid-users-assets-v1-seoul.s3.ap-northeast-2.amazonaws.com/public/capture_images/f598ca893b8e4ebab5aa181708cc3124/248d95d2-a2b1-4cef-bc84-596a7d1d1029.png" alt=""><figcaption></figcaption></figure>

GetMapping 에 들어가면

RequestMapping 어노테이션이 보인다.

<figure><img src="https://slid-users-assets-v1-seoul.s3.ap-northeast-2.amazonaws.com/public/capture_images/f598ca893b8e4ebab5aa181708cc3124/18a3425e-ec74-4cf1-bddd-1e1dff7ba7b0.png" alt=""><figcaption></figcaption></figure>

RequestMapping 을 이용해서 하나로 모아줄수 있다.

<figure><img src="https://slid-users-assets-v1-seoul.s3.ap-northeast-2.amazonaws.com/public/capture_images/f598ca893b8e4ebab5aa181708cc3124/3c1767c6-ecca-4dfe-a2d2-f78b23c323ea.png" alt=""><figcaption></figcaption></figure>

이런식으로 변경할 수 있다.

이후 url 이나 http 로 요청을 테스트를 해본다.



## ✅ RequestMapping

* HTTP 요청을 특정 메소드에 매핑하기 위해 사용된다.
* 이 어노테이션은 컨트롤러 클래스의 메소드에 적용되어, 특정 URL 경로가 해당 메소드에 의해 처리 될 수 있도록 한다.
* value : 클라이언트로부터 들어오는 요청 URL 을 지정합니다.
* method: HTTP 요청 메소드 ( 예: GET,POST 등등 을 지정합니다. )



## ✅ Method Mapping

### GetMapping

```java
@GetMapping("/path")
public String myMethod() {
    // 메소드 내용
}

@GetMapping("/user/{id}")
public String getUserById(@PathVariable String id) {
    // id에 해당하는 사용자 정보를 반환하는 로직
}

// queryString 으로도 받을 수 있다.
@GetMapping("/search")
public String search(@RequestParam String query) {
    // 'query' 파라미터를 사용한 처리 로직
}

@GetMapping("/search")
public String search(@RequestParam(defaultValue = "defaultQuery") String query) {
    // 'query' 파라미터가 없는 경우 'defaultQuery'가 기본값으로 사용됩니다.
}

@GetMapping("/search")
public String search(@RequestParam String query, @RequestParam int page) {
// 'query'와 'page' 파라미터를 사용한 처리 로직
//  /search?query=something&page=1 형태의 URL에서 query와 page 값을 각각의 메소드 파라미터로 전달합니다.
}

```

### PostMapping

```java
@PostMapping("/path")
public String methodName() {
    // 메소드 내용
}

@PostMapping("/user")
public String addUser(@RequestBody User user) {
    // User 객체를 사용하는 로직
}

@PostMapping("/login")
public String login(@RequestParam String username, @RequestParam String password) {
    // @RequestParam: URL 의 쿼리 파라미터나 폼 데이터를 메소드의 파라미터로 받는데 사용
    // 로그인 로직
}


```

### PatchMapping

```java
@PatchMapping("/path/{id}")
public String updatePartial(@PathVariable Long id, @RequestBody PatchRequest patchRequest) {
    // 부분 업데이트 로직
}

```

<mark style="color:orange;">`@PatchMapping("/path/{id}")`</mark>: 클라이언트로부터 `/path/{id}`라는 경로로 들어오는 PATCH 요청을 `updatePartial` 메소드와 매핑합니다.

### DeleteMapping

```java
@DeleteMapping("/path/{id}")
public ResponseEntity<Void> deleteResource(@PathVariable Long id) {
    // 리소스 삭제 로직
    return ResponseEntity.ok().build();
}

@DeleteMapping("/user/{id}")
public ResponseEntity<Void> deleteUser(@PathVariable Long id) {
    // id에 해당하는 사용자를 삭제하는 로직
    // 삭제 로직
    return ResponseEntity.noContent().build();
}


```

### 예외 처리&#x20;

```java
@ExceptionHandler({ExceptionType1.class, ExceptionType2.class})
public ResponseEntity<String> handleMultipleExceptions(RuntimeException e) {
    // 여러 예외 타입에 대한 공통 처리 로직
    return new ResponseEntity<>("Error: " + e.getMessage(), HttpStatus.INTERNAL_SERVER_ERROR);
}

```

* 전역 예외 처리

<mark style="color:orange;">`@ControllerAdvice`</mark> 어노테이션과 함께 <mark style="color:orange;">`@ExceptionHandler`</mark>를 사용하면, 애플리케이션 전체에 걸쳐 예외를 처리할 수 있는 전역 예외 처리기를 만들 수 있습니다. 이 방법은 애플리케이션 내 모든 컨트롤러에서 발생하는 예외를 일관되게 처리할 수 있게 해줍니다.

```java
@ControllerAdvice
public class GlobalExceptionHandler {

    @ExceptionHandler(Exception.class)
    public ResponseEntity<String> handleAllExceptions(Exception e) {
        // 모든 예외에 대한 처리 로직
        return new ResponseEntity<>("Global error: " + e.getMessage(), HttpStatus.INTERNAL_SERVER_ERROR);
    }
}

```



