# tech-interview


## 모든 컬럼에 대해서 index를 걸었을때 단점

- 모든 컬럼에 대해서 인덱스를 걸게 되면 조회 속도는 빠를 수 있지만
- 갱신 삽입 삭제시 인덱스도 수정해야 하기 때문에 속도가 느려지게 된다.
- 대규모 삭제/수정은 배치를 활용한다.


## 과거에 썼던 다른 언어와 javascript 의 차이점

- 과거에 썼던 언어
  - python
  - C#
  - java

3가지 언어 모두 synchronized, 멀티 스레드 기반의 언어였다.
js는 이벤트 기반의 싱글스레드 구조를 갖는다.

정적 언어들처럼 타입이 정해져 있고 컴파일시 문제가 발견되거나 하지 않는다.



## 스택 오버 플로우 에러 정의

자료형이 가질 수 있는 데이터 크기보다 더 큰 데이터를 넣었을때 발생하는 에러



## 이벤트 루프와 Promise의 관계

- 이벤트 루프는 callstack과 node api 사이에서 콜백 함수를 call stack 으로 가져오는 역할을 한다.

- Promise 는 이벤트 루프의 태스크 큐에서 마이크로 태스크 큐로 분류된다.

- 마이크로 태스크는 timer 페이즈에 있는 setTimeout 같은 태스크 함수들보다 먼저 처리된다.



## 이벤트 루프와 Promise의 관계

- 이벤트 루프는 callstack과 node api 사이에서 콜백 함수를 call stack 으로 가져오는 역할을 한다.

- Promise 는 이벤트 루프의 태스크 큐에서 마이크로 태스크 큐로 분류된다.

- 마이크로 태스크는 timer 페이즈에 있는 setTimeout 같은 태스크 함수들보다 먼저 처리된다.



## 함수형 프로그래밍 설명

- 함수의 참조 무결성을 보장하는 순수 함수를 바탕으로 프로그래밍 하는 방식




## blocking io / non blocking io 차이, 장단점

- blocking io는 io 작업시 스레드가 작업을 처리하고 다음 작업을 처리한다.
  - io 작업을 마칠때까지 프로그램이 대기한다.
  - 작업이 완료되면 다음 작업을 수행한다.
  - 장점은 설계가 간단하고 코드가 직관적이다. 쓰기 쉽다.
  - 단점은 프로그램이 대기하게 되므로 사용자 경험이 좋지 않고 자원이 낭비된다.

- non blocking io는 작업 수행시 프로그램이 비동기적으로 다른 일을 처리 할 수 있다.
  - 장점은 io 작업시 프로그램이 대기하지 않아서 더 좋은 사용자 경험을 줄 수 있다.
  - 단점은 프로그램 작성이 blocking io 보다 복잡해질 수 있다.




## Nodejs에서 비동기를 해결하는 방법

- callback
  - 함수를 실행한 결과를 주는 것이 아니라. 작업이 완료된 후에 실행할 함수를 리턴한다.

- promise
  - 비동기적인 작업을 node api가 실행하고 실행에 대한 Promise 객체를 반환한다.
  - Promise 객체는 status가 나눠져 있고 그에따라 개발할 수 있다.
  - fullfilled, reject, pending
  - fullfilled = 작업이 잘 완료됨. then 으로 접근
  - reject = 작업이 문제가 생김. catch 로 접근
  - Pending = 작업 수행중

- async/await
  - 콜백 헬을 없애고 편리하게 비동기 코드를 작성하고자 등장.
  - Promise를 반환하는 함수에 await를 적어서 비동기 코드를 동기식으로 작성 할 수 있다.



## index를 효율적으로 거는 방법

- 3개~5개 정도의 인덱스를 사용한다.
- 카디널리티가 높은 순서대로 인덱스를 지정한다.
- 인덱스의 개수가 1개가 아니라면 복합 인덱스 사용을 고려한다.
- where 절에서 자주 쓰이는 항목은 인덱스 사용을 고려한다.
- 값의 중복도가 낮은 것에 대해서 인덱스를 사용한다.



## MSA 구조의 장점과 단점 - 모놀리틱 서비스와 비교해서

- 장점
  - 기술 이기종성을 가질 수 있다. - 서비스마다 적합한 기술을 선택해서 개발 할 수 있다.
  - 배포와 빌드 시간이 더 짧다.
  - 여러 사람이 작업하기 편리하다. 모놀리틱은 하나의 거대한 코드 베이스를 같이 작업해야 한다.

- 단점
  - 관리하는 복잡도가 증가하게 된다.
  - 버그 발생시 원인 파악이 모놀리틱보다 힘들다.



## n + 1 문제

- 1 : N 관계에서 lazy 로딩을 활용해서 쿼리 했을때 관련된 N개의 행을 N번 쿼리해서 가져오는 문제

- left join 을 써서 해결 할 수 있다.



## 적용했던 디자인 패턴과 왜 쓰는지 어떻게 쓰는지 설명

- 모듈 패턴

적용 전
```
const func1 = function () {
  return 'func';
}
const value = func1();
```

적용 후
```
const value = (function() {
  return 'func';
})();
```
모듈 패턴은 IIFE 함수를 호출해서 따로 변수를 할당하고 호출하지 않게 해준다.


## 다른 언어에서 nodejs로 포팅했을때 다른점, 어려운 점, 바꾼 이유

- 타입 문제
  - 정적으로 타입이 검사되지 않기 때문에 실행후에 버그로 발견되는 부분들이 있다.
  - 테스트 커버리지를 더 높게 작성해서 해결하려고 했다.

- 비동기 코드 작성 문제
  - await 가 없거나 콜백 함수로 인해서 실행흐름을 잘못 작성하게 될 수 있다.

- expressJS 사용시 틀이 없기 때문에 구성원의 코드 품질이 모두 같지는 않을 수 있다.

- 바꾼 이유
  - 언어 차원에서 이벤트 드리븐을 사용 할 수 있다.
  - 이것은 사용하는 스레드의 개수를 크게 늘리지 않고 더 많은 요청을 처리 할 수 있게 해준다.
  - 서버 비용 절감의 효과가 있다.
  - 정적 언어에 비해서 개발 속도가 빠르다.
  - java, C# 대비 30% 정도는 코드의 양이 줄어든다.
  - 오픈 소스 생태계를 활용해서 다양한 모듈들을 적용하고 개발할 수 있다.


## RDB와 Document DB의 차이

- RDB
  - 외래키, 종속 삭제를 지원한다.
  - 정해진 스키마가 있다. 틀에 맞는 데이터만 넣는다.
  - 객체 관계를 바탕으로 설계한다.

- Document DB
  - 쓰기 성능이 비교적 좋다.
  - 종속 삭제를 지원하지 않는다.
  - 정해진 스키마가 없다. 다양한 데이터가 들어 갈 수 있다.
  - 화면에 나오는 데이터를 바탕으로 설계한다.


## REST API의 정의. API 설계 방식

- get post put delete 를 활용한다.
- 자원의 작은 부분을 수정하는 경우 patch api도 활용한다.
- 명사형 url 을 사용한다.
  - /book - post
  - /book/1 - put
  - /book/1 - get
  - /book/1 - patch

- 무상태성을 갖는다.
  - 서버는 각각의 요청을 별개의 요청으로 인식해야 한다.
  - 이전 요청이 다음 요청에 영향을 주어서는 안된다.

- 캐시를 사용할 수 있다.
  - 웹 api이므로 웹에서 사용하는 캐시를 쓸 수 있다.

- server - client 구조를 갖는다.
- self descriptive message
  - rest api 응답 메세지는 스스로 설명할 수 있어야 한다.
- HATEOAS
  - api 메세지는 관련된 정보를 얻을 수 있는 url을 제공해야 한다.

- rest api 는 로드밸런서, 게이트웨이 같은 계층 구조를 가질 수 있다.
