# Data Access

## ✅ DAO(Data Access Object)

<figure><img src="../.gitbook/assets/스크린샷 2023-11-19 오후 5.10.27.png" alt=""><figcaption></figcaption></figure>

실제 데이터에 접근해서 변경하는 부분은 Repository 객체이므로, 이러한 Repository 가 바로 DAO ( Data Access Object) 이다.

엄밀히 말하면 DAO 와 Repository 는 다르다.

## ✅ List

* 순서가 있는 컬렉션이다.
* 내부적으로 동적 배열을 사용하여 요소를 저장한다.
* 요소의 추가 및 인덱스를 통한 접근이 빠르다



<figure><img src="../.gitbook/assets/스크린샷 2023-11-19 오후 4.35.14.png" alt=""><figcaption></figcaption></figure>

### [ArrayList](https://www.nextree.co.kr/p6506/)

ArrayList 는 인덱스를 통한 접근이 매우 빠르다.

ArrayList 는 내부 배열이 꽉 차면 ArrayList 는 더큰 새 배열을 생성하고 기존의 요소들을 새 배열로 복사합니다.

이 과정은 비용이 많이 들어간다.

그래서 요소의 추가 혹은 삭제는 느릴 수 있습니다. 특히 리스트의 중간에 요소를 추가하거나 삭제할 때, 나머지 요소들을 이동시켜야 하기 때문이다.



<figure><img src="../.gitbook/assets/스크린샷 2023-11-19 오후 4.36.17.png" alt=""><figcaption></figcaption></figure>

만약 데이터를 추가하게 될때 , 기존 배열에서 크기가 초과하게 되면 새롭게 배열을 생성하게 된다&#x20;



### LinkedList

LinkedList 는 내부적으로 이중 연결리스트를 사용하여 요소를 저장합니다.

주요 특징

1. 요소의 추가 및 삭제: LinkedList 는 요소의 추가와 삭제가 빠르다.
2. 특히 리스트의 중간에 요소를 추가하거나 삭제할 때 유리하다. 이전/다음 요소의 링크만 변경하면 되기 때문이다.



ArrayList 에서는 무작위 접근이 가능하지만, LinkedList 에서는 순차접근만이 가능하다.

특히, 단순 LinkedList 는 단방향성을 갖고 있기때문에 인덱스를 이용하여 자료를 검색하는 애플리케이션에는 적합하지 않습니다.

사실 순차 접근도 참조의 지역성 ( locality of reference: 전산 이론중의 하나로 한번 참조한 데이터는 다시 참조될 가능성이 높고 참조된 데이터 주변의 데이터 역시 같이 참조될 가능성이 높다는 이론)  때문에 LinkedList 보다는 ArrayList가 훨씬 빠르다.

n개의 자료를 저장할 때, ArrayList 는 자료들을 하나의 연속적인 묶음으로 묶어 자료를 저장하는 반면, LinkedList 는 자료들을 저장 공간에 불연속적인 단위로 저장하게 됩니다. 그렇기 때문에 LinkedList 는 메모리 이곳저곳에 산재해 저장되어 있는 노드들을 접근하는데 ArrayList 보다는 긴 지연 시간이 소모된다.

LinkedList 의 또 다른 단점은 참조자를 위해 추가적인 메모리를 할당해야 하는 점이다.

자료들의 크기가 작은 리스트의 경우 참조자를 위한 추가적인 메모리할당은 비실용적일 수 있다.



## ✅ Map

Map 은 데이터를 키-값 쌍으로 저장합니다. 각 키는 맵 내에서 유일해야한다.

키는 중복 될 수 없습니다. 새로운 키-값 쌍을 추가할 때 이미 존재하는 키를 사용하면, 기존의 값이 새 값으로 대체됩니다. 대부분의 Map 구현체는 요소의 순서를 보장하지 않습니다. 순서를 보장하는 구현체도 있지만 기본적으로 Map 은 순서를 고려하지 않는 데이터 구조이다.



```java
Map<String, Integer> map = new HashMap<>();
map.put("apple", 10);
map.put("orange", 20);

int appleCount = map.get("apple"); // 10
int bananaCount = map.getOrDefault("banana", 0); // 0, "banana" 키가 없으므로 기본값 0 반환

map.remove("orange"); // "orange" 키-값 쌍을 제거

```

