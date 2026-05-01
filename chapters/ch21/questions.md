# ch21 질문 모음

## Q1. 다음의 출력 결과 및 이유는?

```jsx
var globalVar = "I am var";
let globalLet = "I am let";
const globalConst = "I am const";

console.log(globalThis.globalVar);
console.log(globalThis.globalLet);
console.log(globalThis.globalConst);
```

<details>
<summary>정답</summary>

```
"I am var"
undefined
undefined
```

`var`로 선언한 변수는 전역 객체의 프로퍼티로 등록되어 `globalThis`로 접근 가능하다. 반면 `let`과 `const`는 전역 렉시컬 환경의 선언적 환경 레코드에 저장되어 전역 객체의 프로퍼티가 아니므로 `globalThis`로 접근할 수 없다.

초기 자바스크립트는 구현 단순화를 위해 전역 변수를 전역 객체 프로퍼티에 저장했으나(var), ES6에서 `let`/`const` 도입 시 전역 객체 오염 문제를 막기 위해 별도 공간으로 분리했다.

</details>

---

## Q2. eval 함수 사용이 금지되는 이유는?

<details>
<summary>정답</summary>

- **보안 취약점**: 문자열을 코드로 직접 실행하므로 외부 입력값이 그대로 실행될 경우 스크립트 인젝션 공격에 노출된다.
- **성능 저하**: 런타임에 코드를 동적으로 해석하므로 JS 엔진의 정적 분석 기반 최적화(tree shaking 등)가 불가능하다.
- **스코프 오염**: strict mode가 아닌 경우 `eval` 내부에서 선언한 변수가 외부 스코프에 영향을 줄 수 있다.

</details>

---

## Q3. 브라우저와 Node.js 환경에서 각각 전역 객체를 지칭하는 이름은?

<details>
<summary>정답</summary>

- 브라우저: `window`
- Node.js: `global`
- 공통 통합 식별자: `globalThis` (ES11 도입, 환경에 관계없이 전역 객체를 가리킴)

</details>
