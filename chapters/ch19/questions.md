# ch19 문제 모음

## Q1. `in` 연산자와 `hasOwnProperty`의 차이를 설명하시오.

<details>
<summary>정답</summary>

| | `in` | `hasOwnProperty` |
| --- | --- | --- |
| 자신의 프로퍼티 | ✅ | ✅ |
| 상속된 프로퍼티 | ✅ | ❌ |

- `in`: 프로토타입 체인 전체를 탐색해 프로퍼티 존재 여부를 확인한다.
- `hasOwnProperty`: 객체 자신의 프로퍼티인 경우에만 `true`를 반환한다.

```jsx
function Person() {}
Person.prototype.name = 'Lee';
const me = new Person();

'name' in me;              // true  (상속된 프로퍼티 포함)
me.hasOwnProperty('name'); // false (자신의 프로퍼티 아님)
```

</details>
