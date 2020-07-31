#### REST API의 정의. API 설계 방식

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
  


