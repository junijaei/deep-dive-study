# Week 04

## 진행범위
- ch20 ~ ch22

## 요약 문서
- [ch20](../chapters/ch20/README.md)
- [ch21](../chapters/ch21/README.md)
- [ch22](../chapters/ch22/README.md)

## 핵심 요약
- strict mode는 전역/함수 단위 적용을 피하고, 즉시 실행 함수로 스코프를 구분해 적용한다.
- strict mode에서 일반 함수의 this는 undefined, 선언 없는 변수 할당은 ReferenceError가 발생한다.
- 원시값에 마침표 접근 시 엔진이 **래퍼 객체**를 임시 생성하고, 접근 후 즉시 폐기한다.
- `globalThis`는 브라우저(window)와 Node.js(global) 환경 모두에서 전역 객체를 가리키는 통합 식별자다.
- this 바인딩은 **함수 호출 시점**에 동적으로 결정된다 (렉시컬 스코프는 함수 정의 시점과 대조).
- `apply`/`call`은 함수를 즉시 호출하며 this를 교체, `bind`는 this가 교체된 새 함수를 반환한다.
