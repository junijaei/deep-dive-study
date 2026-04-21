# ch18 문제 모음

## Q1. 아래 두 함수의 `name` 프로퍼티 값은 각각 무엇인가?

```jsx
const a = function foo() {};
const b = function () {};
```

<details>
<summary>정답</summary>

- `a.name` → `'foo'` (기명 함수 표현식은 함수 이름을 그대로 사용)
- `b.name` → `'b'` (ES6부터 익명 함수 표현식은 할당된 변수 이름으로 추론)

ES5에서 `b.name`은 빈 문자열(`''`)이다.

</details>

---

## Q2. 화살표 함수에서 `arguments` 객체를 사용할 수 없는 이유와 대안을 설명하시오.

<details>
<summary>정답</summary>

화살표 함수는 `arguments` 객체를 가지지 않는다. 화살표 함수는 `this`, `arguments`, `super`, `new.target`을 바인딩하지 않도록 설계되었기 때문이다.

대안으로 Rest 파라미터를 사용한다.

```jsx
const foo = (...args) => {
  console.log(args); // 일반 배열
};
```

</details>
