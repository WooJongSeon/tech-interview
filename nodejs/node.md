## Nodejs 질문

### (기술)제너레이터에 대해 설명해보세요. 어떤 상황에서 활용할 수 있을지 얘기해보세요.



### (캐주얼)왜 개발자가 되었는지?

### 인덱스를 효율적으로 거는 방법은?

### 테이블당 3~5개 정도가 적당 카디널리티(값의 다양성) ↑ 선택도(고유할수록 좋음) ↓ 활용도(where절에 자주 사용됨) ↑ 중복도(같은 컬럼에 대해 중복생성X) ↓

### 이벤트루프와 promise의 관계에 대해 설명 해보세요.
- [답](#event-loop)





dasfasdfasddsa

dasfasdfasddsa
dasfasdfasddsa
dasfasdfasddsa
dasfasdfasddsa
dasfasdfasddsa
dasfasdfasddsa




dasfasdfasddsa
dasfasdfasddsa
dasfasdfasddsa
dasfasdfasddsa
dasfasdfasddsa
dasfasdfasddsa

dasfasdfasddsa
dasfasdfasddsa
dasfasdfasddsa
dasfasdfasddsa
dasfasdfasddsa
dasfasdfasddsa

dasfasdfasddsa
dasfasdfasddsa
dasfasdfasddsa
dasfasdfasddsa
dasfasdfasddsa
dasfasdfasddsa

dasfasdfasddsa
dasfasdfasddsa
dasfasdfasddsa
dasfasdfasddsa
dasfasdfasddsa
dasfasdfasddsa

dasfasdfasddsa
dasfasdfasddsa
dasfasdfasddsa
dasfasdfasddsa
dasfasdfasddsa
dasfasdfasddsa

dasfasdfasddsa
dasfasdfasddsa
dasfasdfasddsa
dasfasdfasddsa
dasfasdfasddsa
dasfasdfasddsa

dasfasdfasddsa
dasfasdfasddsa
dasfasdfasddsa
dasfasdfasddsa
dasfasdfasddsa
dasfasdfasddsa

dasfasdfasddsa
dasfasdfasddsa
dasfasdfasddsa
dasfasdfasddsa
dasfasdfasddsa
dasfasdfasddsa

dasfasdfasddsa
dasfasdfasddsa
dasfasdfasddsa
dasfasdfasddsa
dasfasdfasddsa
dasfasdfasddsa











































## 해답
[event-loop]#### 이벤트루프와 promise의 관계에 대해 설명 해보세요.

```
Promise는 태스크 큐보다 더 높은 우선순 위를 갖는 마이크로 태스크 큐에 추가됨. setTimeout(function() { // (A)
console.log('A'); }, 0);
Promise.resolve().then(function() { // (B) console.log('B');
}).then(function() { // (C) console.log('C');
});
```
