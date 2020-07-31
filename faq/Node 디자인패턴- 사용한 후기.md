#### 적용했던 디자인 패턴과 왜 쓰는지 어떻게 쓰는지 설명

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

##### 모듈 패턴은 IIFE 함수를 호출해서 따로 변수를 할당하고 호출하지 않게 해준다.
