# Week 06

## 진행 범위

- ch25 ~ ch26

## 요약 문서

- [ch25](../chapters/ch25/README.md)
- [ch26](../chapters/ch26/README.md)

## 핵심 요약

- 자바스크립트 클래스는 프로토타입 기반 상속의 문법적 설탕이지만, 생성자 함수와 달리 반드시 `new`로만 호출해야 하며 암묵적으로 strict mode가 적용된다.
- 클래스 필드(`#` private, `static`)는 ES2022에 표준화되어 constructor 외부에서도 인스턴스/정적 프로퍼티를 선언할 수 있다.
- 서브클래스 constructor에서 `super()` 호출 전 `this` 참조는 불가능하다. 인스턴스 생성은 수퍼클래스가 담당하고 `super()`가 반환한 객체가 서브클래스의 `this`에 바인딩된다.
- ES6에서 함수를 일반 함수/메서드/화살표 함수로 구분하여 사용 목적에 맞지 않는 호출을 방지한다.
- 화살표 함수는 자체 `this` 바인딩이 없으며, 내부의 `this`는 상위 스코프의 `this`를 그대로 참조한다(lexical this).
- Rest 파라미터는 인수 목록을 **배열**로 받아 `arguments` 유사 배열 문제를 해결한다.
