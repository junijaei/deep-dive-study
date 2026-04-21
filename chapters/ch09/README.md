## 9. 타입 변환과 단축 평가

### 9.4.3 null 병합 연산자

- `??` 는 좌항의 피연산자가 null 또는 undefined인 경우 우항의 피연산자를 반환한다.
- 논리 연산자(||)와 null 병합 연산자(??)의 차이
    - 논리 연산자(||): 좌항의 피연산자가 Falsy값이면 우항의 피연산자 반환
    - null 병합 연산자(??): 좌항의 피연산자가 Falsy여도 null이나 undefined가 아니면 좌항의 피연산자 반한

```jsx
var foo = '' || 'default string';
console.log(foo); // 'default string'

var boo = '' ?? 'default string';
console.log(boo); // ''
```