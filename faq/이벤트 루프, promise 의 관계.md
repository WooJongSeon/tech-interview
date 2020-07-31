#### 이벤트 루프와 Promise의 관계

- 이벤트 루프는 callstack과 node api 사이에서 콜백 함수를 call stack 으로 가져오는 역할을 한다.

- Promise 는 이벤트 루프의 태스크 큐에서 마이크로 태스크 큐로 분류된다.

- 마이크로 태스크는 timer 페이즈에 있는 setTimeout 같은 태스크 함수들보다 먼저 처리된다.
