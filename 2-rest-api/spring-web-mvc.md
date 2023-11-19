# Spring Web MVC

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



