# 20. strict mode

## 20.1. strict mode란?

- 자바스크립트 언어의 문법을 좀 더 엄격히 적용하는 것
    - eslint와 유사한 효과

## 20.2. strict mode의 적용

- 전역 선두 또는 함수 몸체의 선두에 `'use strict';` 추가하기
- ES6의 클래스와 모듈에서는 기본적으로 적용됨.

## 20.3. 전역에 strict mode를 적용하는 것은 피하자

왜?!

- 스크립트 단위로 적용된 strict mode는 해당 스크립트에 한정되어 적용됨
- 하지만 strict mode 스크립트와 non-strict mode 스크립트를 혼용하는 것은 오류를 발생시킬 수 있다. (왜?!)
- 대신 즉시 실행 함수로 스코프를 구분해 적용하자

## 20.4. 함수 단위로 strict mode를 적용하는 것도 피하자

> strict mode 의미가 있는거임?

- strict mode가 적용된 함수의 외부 컨텍스트에 strict mode가 없다면 곤란해짐

## 20.5. strict mode가 발생시키는 에러

### 20.5.1. 암묵적 전역

> [!NOTE]
> 암묵적 전역
> 변수의 선언없이 변수에 할당하면 전역 프로퍼티에 임의로 변수를 동적 생성하는 것

- 선언하지 않은 변수를 참조하면 `ReferenceError`가 발생한다.

### 20.5.2. 변수, 함수, 매개변수의 삭제

- `delete` 연산자로 변수, 함수, 매개변수를 삭제하면 `SyntaxError`가 발생한다.

### 20.5.3. 매개변수 이름의 중복

- 중복된 매개변수 이름을 사용하면 `SyntaxError`가 발생한다.

### 20.5.4. with문의 사용

- `with`문을 사용하면 `SyntaxError`가 발생한다.

> [!NOTE]
> with문
>
> `with` 문은 객체의 프로퍼티를 **마치 지역 변수처럼 직접 접근할 수 있게 해주는 문법**이다.
>
> - 예시
>
>     ```jsx
>     const user = {
>       name: 'Alice',
>       age: 25,
>     };
>     
>     with (user) {
>       console.log(name); // user.name
>       console.log(age);  // user.age
>     }
>     ```
>
> - 문제점
>     - 스코프가 모호해짐
>
>         ```jsx
>         const name = 'Bob';
>         
>         with (user) {
>           console.log(name); // user.name인지 외부 name인지 불명확
>         }
>         ```
>
>     - 최적화 성능 저하
>         - 변수가 런타임에 해석됨 → 정적 분석 기반 최적화 불가 (번들러 tree shaking 등)
>         - with문 내부에서 호출한 변수가 객체에 없는 프로퍼티라면 전역변수까지 찾아야 함
>     - strict mode에서 사용 불가

## 20.6. strict mode 적용에 의한 변화

### 20.6.1. 일반 함수의 this

- strict mode에서 함수를 일반 함수로 호출하면 this에 undefined가 바인딩됨.
    - 일반 함수는 this를 사용할 필요가 없기 때문

```jsx
(
	function() {
		'use strict';
		
		function foo() {
			console.log(this); // undefined
		}
		foo();
		
		function Foo() {
			console.log(this); // Foo
		}
		new Foo();
	}
());
```

### 20.6.2. arguments 객체

- 매개변수에 전달된 인수를 재할당하여 변경해도 arguments 객체에 반영되지 않는다.

> 원랜 반영됐다고?
