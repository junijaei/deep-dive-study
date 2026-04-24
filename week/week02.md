# Week 02

## 진행 범위

- ch11 ~ ch16

## 요약 문서

- [ch11](../chapters/ch11/README.md)
- [ch12](../chapters/ch12/README.md)

## 핵심 요약

- 원시 값은 **변경 불가능한 값**으로 변수에 실제 값이 저장되고, 객체는 **변경 가능한 값**으로 변수에 참조 값이 저장된다.
- 원시 값 재할당 시 기존 메모리를 수정하는 게 아니라 **새 메모리 공간을 확보**해 값을 저장한다.
- 원시 값 변수를 다른 변수에 할당하면 **값에 의한 전달**, 객체 변수를 할당하면 **참조에 의한 전달**이 일어난다.
- 히든 클래스는 ECMAScript 명세 밖의 엔진 최적화 메커니즘으로, 객체의 프로퍼티 구조를 매핑해 성능을 개선한다.
- 함수 선언문은 런타임 이전에 호이스팅되지만, 함수 표현식은 변수 호이스팅만 발생해 런타임에 할당된다.
- 함수 선언문으로 정의한 함수 이름은 함수 몸체 내에서만 유효하며, 외부 호출에 쓰이는 식별자는 엔진이 암묵적으로 생성한다.

## 토론 내용

### `const`와 객체 프로퍼티 수정의 혼란

- `const`는 재할당만 막을 뿐 객체 프로퍼티 수정은 허용한다.
- 진정한 불변 객체가 필요하다면 `Object.freeze` 같은 동결 메서드를 별도로 사용해야 한다.
- 실제로 협업 중 `const`로 선언한 변경 가능한 객체를 두고 혼란이 생긴 경험이 있다.

### `Object.preventExtensions` / `Object.seal` / `Object.freeze` 실사용

- 실무에서 직접 사용한 경험은 드물다.
- JS 코어 레벨 시스템 구축이나 셀렉트 컴포넌트의 옵션 상수 관리 시 활용할 수 있다.
- `deepFreeze` 구현 시 `Object.keys` 대신 `Reflect.ownKeys`를 쓰는 이유:
  - `Object.keys`는 `symbol` 키와 `non-enumerable` 프로퍼티를 탐색하지 못한다.
  - `Reflect.ownKeys`는 문자열 키, `symbol` 키, `non-enumerable` 프로퍼티를 모두 탐색한다.

    ```jsx
    function deepFreeze(obj) {
      Object.freeze(obj);

      Reflect.ownKeys(obj).forEach((key) => {
        deepFreeze(obj[key]);
      });

      return obj;
    }
    ```

### 함수의 생명보다 긴 변수의 생명주기

- 클로저를 통해 외부 함수 실행이 끝나도 내부 변수는 살아남을 수 있다.

  ```jsx
  function outer() {
    let count = 0;

    return function inner() {
      count++;
      console.log(count);
    };
  }

  const fn = outer(); // outer 실행 끝남
  fn(); // 1
  fn(); // 2
  fn(); // 3
  // count는 inner가 참조하는 한 GC되지 않는다
  ```
