---
description: Serialization
---

# 직렬화



{% embed url="https://ko.wikipedia.org/wiki/%EC%A7%81%EB%A0%AC%ED%99%94" %}

{% embed url="https://ko.wikipedia.org/wiki/%EB%A7%88%EC%83%AC%EB%A7%81_(%EC%BB%B4%ED%93%A8%ED%84%B0_%EA%B3%BC%ED%95%99)" %}

객체를 그 자체로 DB에 저장하거나 네트워크로 전송하는 건 불가능.

객체를 복구할 수 있도록 데이터화하는 게 필요함.

바이너리라면 Byte Stream, 텍스트라면 기계가 파싱할 수 있고 사람도 읽을 수 있는 형태를 사용.

XML, JSON 같은 형식이 인기.

직렬화와 마샬링은 거의 같지만, Java에선 마샬링을 특수하게 다룸.

* 직렬화(Serialization): 역직렬화(Deserialization) 를 통해 객체 또는 데이터의 복사본을 만들 수 있음
* 마샬링( Marshalling): 직렬화와 같거나, 원격 객체로 복원할 수 있음. 원격 객체의 경우 메서드 호출은 RPC( 또는 RMI ) 가 됨.



## ✅ JSON ( JavaScript Object Notation )



{% embed url="https://en.wikipedia.org/wiki/JSON" %}

{% embed url="https://www.json.org/json.ko.html" %}

{% embed url="https://developer.mozilla.org/ko/docs/Learn/JavaScript/Objects/JSON" %}

JavaScript Good Parts로 유명한 Douglas Crockfor가 만든 데이터 포맷, 사람이 읽기 쉽고, 기계도 해석또는 생성하기 쉽다.

보안 문제만 없다면 JavaScript에서 그대로 사용하는 것도 가능하지만, 대부분 JSON.parse(역직렬화) 와 JSON.stringify(직렬화)로 안전하게 사용한다.



JavaScript의 object 는 기본적으로 key-value 쌍이다.

(심지어 Array 도 제한된 key-value + length 관리에 불과함) Java 는 Map 이 이와 유사하지만, 스키마 관리 및 타입 안전성을 위해 DTO 를 활용한다.

* 생성: DTO -> 변환기 ->   JSON 문자열
* 해석: JSON 문자열 -> 변환기 -> DTO

