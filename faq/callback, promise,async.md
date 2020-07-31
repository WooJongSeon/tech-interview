#### Nodejs에서 비동기를 해결하는 방법

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
