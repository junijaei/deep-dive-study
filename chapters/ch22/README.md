# 22. this

## 22.1. this 키워드

- 메서드가 자신이 속한 객체의 프로퍼티를 참조하려면 먼저 자신이 속한 객체를 가리키는 식별자를 참조할 수 있어야 한다
- this는 **자신이 속한 객체 또는 자신이 생성할 인스턴스**를 가리키는 **자기 참조 변수**다
- this 바인딩은 함수 호출 방식에 의해 **동적으로 결정된다**

    ```jsx
    console.log(this); // window
    
    function foo() {
    	console.log(this); // window
    }
    
    const person = {
    	name: 'Lee',
    	getName() {
    		console.log(this); // { name: 'Lee', getName: f }
    		return this.name
    	}
    };
    
    function Person(name) {
    	this.name = name;
    	console.log(this); // Person { name: 'Lee' }
    };
    const me = new Person('Kim');
    ```

## 22.2. 함수 호출 방식과 this 바인딩

> [!NOTE]
> 렉시컬 스코프와 this 바인딩은 결정 시기가 다르다.
> - 렉시컬 스코프: 함수 정의가 평가되어 함수 객체가 생성되는 시점에 상위 스코프 결정
> - this 바인딩: 함수 호출 시점

### 22.2.1. 일반 함수 호출

- 기본적으로 전역 객체가 바인딩된다 (strict mode에선 undefined)
- 일반 함수로 호출된 모든 중첩 함수, 콜백 함수 또한 전역 객체가 바인딩된다
- this 바인딩을 위한 방법
    - this를 다른 식별자에 담아서 참조하도록 하기
    - apply, call, bind 함수 사용하기
    - 화살표 함수 사용하기

### 22.2.2. 메서드 호출

- 마침표 연산자로 메서드 호출시 **마침표 앞에 있는 객체**가 this로 바인딩됨

### 22.2.3. 생성자 함수 호출

- 생성자 함수가 미래에 생성할 인스턴스가 바인딩된다
- new 연산자와 함께 호출하지 않으면 일반 함수 호출이어서 전역 객체(또는 undefined)가 바인딩된다

### 22.2.4. Function.prototype.apply/call/bind 메서드에 의한 간접 호출

```jsx
/**
* 주어진 this 바인딩과 인수 리스트 배열을 사용하여 함수를 호출한다
*/
Function.prototype.apply(thisArg[, argsArray])

/**
* 주어진 this 바인딩과 ,로 구분된 인수 리스트를 사용하여 함수를 호출한다
*/
Function.prototype.call(thisArg[, args1[, args2, ...]]])
```

- apply와 call의 본질적인 기능은 함수를 호출하는 것이다.

```jsx
/**
* 주어진 this 바인딩을 사용하여 this 바인딩이 교체된 함수를 반환한다
*/
Function.prototype.bind(thisArg)
```
