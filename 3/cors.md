# CORS



## CORS 란



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
