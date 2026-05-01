# ch22 질문 모음

## Q1. 다음의 출력 결과는?

```jsx
function Person(name) {
  this.name = name;
}

const p1 = Person('Lee');
console.log(p1);
console.log(window.name);
```

<details>
<summary>정답</summary>

```
undefined
"Lee"
```

`Person`을 `new` 없이 일반 함수로 호출했으므로 반환값이 없어 `p1`은 `undefined`다. 일반 함수 호출 시 `this`는 전역 객체(`window`)에 바인딩되므로 `this.name = 'Lee'`는 `window.name`에 할당된다.

</details>

---

## Q2. 다음의 출력 결과는?

```jsx
const obj = {
  value: 10,
  getValue() {
    return this.value;
  }
};

const fn = obj.getValue;

console.log(obj.getValue());
console.log(fn());
```

<details>
<summary>정답</summary>

```
10
undefined
```

`obj.getValue()`는 메서드 호출이므로 `this`는 `obj`에 바인딩되어 `obj.value`인 `10`을 반환한다. `fn()`은 일반 함수 호출이므로 `this`는 전역 객체에 바인딩되고, 전역에 `value` 프로퍼티가 없으므로 `undefined`를 반환한다.

</details>

---

## Q3. `apply`, `call`, `bind`의 공통점과 차이점은?

<details>
<summary>정답</summary>

**공통점**: 모두 `Function.prototype`의 메서드로, 함수의 `this`를 명시적으로 지정한다.

**차이점**:

| | `apply` | `call` | `bind` |
| --- | --- | --- | --- |
| 함수 실행 | 즉시 실행 | 즉시 실행 | 실행 X |
| 인수 전달 | 배열로 전달 | 쉼표로 전달 | 쉼표로 전달 |
| 반환값 | 함수 실행 결과 | 함수 실행 결과 | this가 고정된 새 함수 |

</details>
