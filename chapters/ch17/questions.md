# ch17 문제 모음

## Q1. 화살표 함수가 `new`로 호출될 수 없는 이유를 설명하시오.

<details>
<summary>정답</summary>

함수 객체는 내부 메서드 `[[Call]]`과 `[[Construct]]`를 가진다.

- 함수 선언문: `[[Call]]` + `[[Construct]]` 모두 있음 → `new` 사용 가능 (constructor)
- 화살표 함수: `[[Call]]`만 있음 → `new` 사용 불가 (non-constructor)

`[[Construct]]`가 없으면 `new`로 인스턴스를 만들 수 없고, 인스턴스를 만들 수 없으면 `prototype`도 필요 없으므로 화살표 함수에는 `prototype` 프로퍼티도 없다.

</details>

---

## Q2. 생성자 함수 내부에서 아래 두 `return`을 명시하면 각각 어떻게 되는지 설명하시오.

```jsx
// 케이스 1
function Person() {
  return { name: '철수' };
}

// 케이스 2
function Person() {
  return 100;
}
```

<details>
<summary>정답</summary>

- `return { name: '철수' }` → 명시한 객체가 반환된다. (`this` 무시)
- `return 100` → 원시값 반환은 무시되고 `this`가 반환된다.

생성자 함수 내부에서 `return`은 쓰지 않는 것이 원칙이다.

</details>
