# 17. 생성자 함수에 의한 객체 생성

## 17.2. 생성자 함수

- 동일한 프로퍼티를 가진 객체를 여러개 만들 경우, 객체 리터럴을 통한 생성 방식은 비효율적임
    
    ```jsx
    const circle1 = {
    	radius: 5,
    	getDiameter() {
    		return 2 * this.radius;
    	}
    }
    
    const circle2 = {
    	radius: 5,
    	getDiameter() {
    		return 2 * this.radius;
    	}
    }
    
    ...
    ```
    
    - 매번 같은 프로퍼티와 메서드를 기술해야 함
- 생성자 함수를 통해 객체를 생성하면 여러개의 객체를 간편하게 생성할 수 있다.
    
    ```jsx
    function Circle(radius) {
    	this.radius = radius;
    	this.getDiameter = function() {
    		return 2 * this.radius;
    	};
    }
    
    const circle1 = new Circle(5);
    const circle2 = new Circle(10);
    ...
    ```
    

> [!NOTE]
> this
> | 함수 호출 방식 | this가 가리키는 값 |
> | --- | --- |
> | 일반 함수로서 호출 | 전역 객체 |
> | 메서드로서 호출 | 메서드를 호출한 객체(마침표 앞의 객체) |
> | 생성자 함수로서 호출 | 생성자 함수가 (미래에) 생성할 인스턴스 |

- 일반 함수와 동일한 방법으로 함수를 생성하고, `new`를 붙여 호출하면 해당 함수는 생성자 함수로 동작

### 17.2.3. 생성자 함수의 인스턴스 생성 과정

- `new` 와 함께 함수를 호출하면 생성자 함수의 동작을 자바스크립트 엔진이 암묵적으로 처리한다.
1. 인스턴스 생성과 this 바인딩
    1. 빈 객체 생성
    2. this 바인딩
2. 인스턴스 초기화
    1. 생성자 함수 내부 로직 실행 (개발자의 몫)
3. 인스턴스 반환
    1. this를 암묵적으로 반환
    2. 다른 객체를 명시적으로 반환한다면 그 객체가 반환됨

### 17.2.4. 내부 메서드 `[[Call]]`과 `[[Construct]]`

- 함수는 객체여서 내부 프로퍼티와 메서드를 가질 수 있다.
- 일반 객체와 달리 함수는 호출할 수 있다.
    - 함수는 일반 객체와 달리 내부 슬롯 `[[Environment]]` 와 `[[FormalParameters]]` , 내부 메서드 `[[Call]]`과 `[[Construct]]` 를 가진다.
- 함수가 일반 함수로서 호출되면 `[[Call]]` 이 호출되고, 생성자 함수로 호출되면 `[[Construct]]` 이 호출된다.
- 모든 함수 객체는 callable이지만 모든 함수 객체가 constructor인 건 아니다.

### 17.2.5. constructor와 non-constructor의 구분

- constructor: 함수 선언문, 함수 표현식, 클래스
- non-constructor: 메서드, 화살표 함수
    - ES6의 메서드 축약 표현만 메서드로 인정된다.
    
    ```jsx
    const obj1 = {
    	x: function () {} // 메서드 아님
    }
    
    const obj2 = {
    	x() {} // 메서드임
    }
    ```
    
    - non-constructor 함수를 new 연산자와 함께 호출하면 타입 에러가 난다.

### 17.2.7. new.target

- 생성자 함수가 new와 함께 사용되었는지 확인하기 위한 메타 프로퍼티
    - 생성자 함수로 호출되었을 경우: new.target → 함수 자신
    - 일반 함수로 호출되었을 경우: new.target → undefined
- IE에서는 지원되지 않는 문법이다.
    - new.target을 사용할 수 없는 상황이라면 스코프 세이프 생성자 패턴을 사용할 수 있다.
    
    ```jsx
    function Circle(radius) {
    
    	if (!(this instanceof Circle)) {
    		return new Circle(radius);
    	}
    
    	this.radius = radius;
    	this.getDiameter = function() {
    		return 2 * this.radius;
    	};
    }
    ```
    
- Object와 Function 생성자 함수는 new 연산자 없이 호출해도 생성자 함수로서 동작한다.
- 하지만 String, Number, Boolean 함수는 new 연산자 없이 사용했을 때 문자열, 숫자, 불리언 값을 반환한다.
