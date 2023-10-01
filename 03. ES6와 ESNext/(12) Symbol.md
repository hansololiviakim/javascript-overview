# 12. Symbol

## 12.1 정의

- ES6에서 도입된 JavaScript의 원시 데이터 타입 중 하나

- `고유하고 변경 불가능한 값`을 나타냄

- 주로 `객체의 프로퍼티 키`로 사용되며, 해당 프로퍼티는 다른 프로퍼티와 충돌하지 않는 `고유한 식별자`를 가짐

<br/><br/>

## 12.2 도입 이유

### 12.2.1 고유 식별자 생성

- Symbol은 고유하며 변경 불가능한 값을 나타내므로 다른 프로퍼티 키와 충돌하지 않는 `고유한 식별자를 생성`할 수 있음

- 이는 `객체의 프로퍼티를 숨기고 보호`하거나, `다른 코드와의 충돌을 방지`하기 위해 사용됨

<br/>

### 12.2.2 프로퍼티 이름 충돌 해결

- JavaScript에서 다양한 라이브러리와 모듈이 함께 사용될 때, 프로퍼티 이름 충돌 문제가 발생할 수 있음

- Symbol 사용 시 다른 라이브러리 또는 모듈과 충돌하지 않고 프로퍼티를 생성할 수 있으므로 `코드 간의 결합도를 낮출 수 있음`

<br/>

### 12.2.3 메타프로그래밍과 확장성

- 메타프로그래밍 _(프로그램의 동작을 조작하는 프로그래밍)_ 에 유용함

- Symbol을 사용해 `객체의 동작을 커스터마이징`하거나 `확장`하는데 사용할 수 있음

<br/>

### 12.2.4 내장된 Symbol과 라이브러리 사용

- JavaScript에서 내장된 Symbol들 _(Symbol.inerator, Symbol.toStringTag 등)_ 은 객체의 동작을 정의하고 특정 목적을 위해 사용됨

- 이러한 내장된 Symbol들은 라이브러리나 프레임워크에서도 활용되어 객체의 행동을 커스터마이징하고 구분하기 위해 사용됨

<br/>

### 12.2.5 표준화와 확장성

- ECMAScript 표준에 추가되어 JavaScript 개발자들에게 표준화된 방법으로 고유한 식별자를 생성하고 활용할 수 있는 기능을 제공

- 이로 인해 JavaScript 언어의 확장성이 향상되며, 다양한 상황에서 사용할 수 있음

<br/>

### 12.2.6 정리

- JavaScript의 객체와 프로퍼티 관리를 보다 유연하게 만듦

- 고유한 식별자를 생성하는데 사용

- 메타프로그래밍과 라이브러리 개발에 유용한 도구로 활용

- JavaScript의 확장성과 표준화를 향상시키는데 기여

<br/><br/>

## 12.3 주요 용도

### 12.3.1 객체 프로퍼티 식별자

- Symbol을 사용해 객체의 프로퍼티를 고유하게 식별하거나, 다른 코드와 충돌하지 않는 식별자를 생성할 수 있음

<br/>

### 12.3.2 Well-known Symbol

- 일부 내장된 Symbol은 특정 동작을 나타내며, 이를 사용해 `객체의 행동을 커스터마이징`할 수 있음

<br/>

### 12.3.3 Private 멤버

- Symbol을 활용해 객체의 priviate한 프로퍼티 또는 메서드를 구현할 수 있음

- 외부에서 읽거나 수정할 수 없는 프로퍼티를 생성

- 캡슐화와 은닉화를 구현하는데 유용한 도구로 사용될 수 있음 <br/>
  👉 객체의 상태를 보호하고 객체의 인터페이스를 추상화하여 외부 코드에 필요한 정보만 노출할 수 있도록 함

<br/>

<details>
  <summary><b>[참고] Symbol의 은닉화와 캡슐화</b></summary><br/>

> **📌 은닉화 (Encapsulation)** <br/>
>
> - 객체 내부 상태와 구현 세부사항을 외부에서 숨기는 것 <br/>
> - 객체 내부의 데이터와 메서드는 외부에서 직접 접근하거나 수정할 수 없으며, 객체의 인터페이스를 통해서만 상호작용할 수 있음 <br/>
> - 데이터 무결성 보호 <br/>
> - 구현 세부사항 은닉하여 사용자에게 추상화된 인터페이스 제공 _(따라서 객체의 구현이 변경되더라도 외부 코드에 미치는 영향을 최소화할 수 있음)_ <br/><br/>
>
> **👉 Symbol의 은닉화** <br/>
>
> - Symbol은 객체의 프로퍼티를 외부에서 직접적으로 접근하기 어렵게 만듦 <br/>
> - 따라서 Symbol을 사용해 객체의 프로퍼티를 `은닉`하면 외부 코드가 해당 프로퍼티에 직접 접근할 수 없으며, 내부적으로만 사용됨 <br/>
> - 이를 통해 객체의 상태를 보호하고 유지보수성을 높일 수 있음 <br/><br/>
>
> **👉 Symbol 은닉화의 예시** <br/>
>
> ```javascript
> const privateSymbol = Symbol('privateProperty');
>
> class MyClass {
>   constructor() {
>     this[privateSymbol] = 'This is a private property';
>   }
>
>   getPrivateProperty() {
>     return this[privateSymbol];
>   }
> }
>
> const instance = new MyClass();
> console.log(instance.getPrivateProperty()); // "This is a private property"
> console.log(instance[privateSymbol]); // undefined (외부에서 직접 접근 불가)
> ```
>
> - 위의 코드는 Symbol을 사용해 private한 프로퍼티를 생성한 예제 <br/>
> - privateSymbol을 사용해 privateProperty를 은닉함 <br/>
> - 외부에서 [privateSymbol]을 직접 접근할 수 없으며, getPrivateProperty 메서드를 통해서만 접근할 수 있음 <br/><br/>
>
> **📌 캡슐화 (Abstraction)** <br/>
>
> - 객체의 상태와 동작을 하나의 단위로 묶어 추상화된 인터페이스를 제공하는 것 <br/>
> - 객체는 자체 데이터와 해당 데이터를 조작하는 메서드를 포함해 하나의 캡슐로 간주됨 <br/>
> - 이로써 객체의 내부 세부사항을 숨기고 외부 코드에 필요한 기능만 노출 가능 <br/>
> - 사용자에게 명확하고 간결한 인터페이스를 제공해 복잡성을 숨기고 코드를 단순화 <br/><br/>
>
> **👉 Symbol의 캡슐화** <br/>
>
> - Symbol은 객체의 프로퍼티를 고유한 식별자로 만드므로 다른 프로퍼티와의 충돌을 방지하고, 객체를 더 추상적으로 나타내는데 사용할 수 있음 <br/>
> - 이는 객체의 인터페이스를 단순화하고, 사용자에게 필요한 정보만 노출하는데 도움 <br/><br/>
>
> **👉 Symbol 캡슐화의 예시** <br/>
>
> ```javascript
> const internalSymbol = Symbol('internalMethod');
>
> class MyAPI {
>   constructor() {
>     // ...
>   }
>
>   [internalSymbol]() {
>     // 내부 로직
>   }
>
>   publicMethod() {
>     // 공개 메서드
>     this[internalSymbol](); // 내부 메서드 호출
>   }
> }
>
> const api = new MyAPI();
> api.publicMethod(); // 외부에서 공개된 메서드만 호출 가능
> api[internalSymbol](); // 오류! (외부에서 직접 접근 불가)
> ```
>
> - 위의 코드는 Symbol을 사용해 구현 내용을 캡슐화해 클래스 내부 구현에 대한 세부사항을 숨기고 공개 인터페이스만 제공한 예제 <br/>
> - internalSymbol을 사용해 내부 메서드를 캡슐화 <br/>
> - 따라서 외부에서는 publicMethod만 호출할 수 있고, 내부 메서드는 숨겨져 있음 <br/><br/>

</details>

<br/><br/>

## 12.4 주요 특징 및 사용법

### 12.4.1 Symbol의 생성

```javascript
const mySymbol = Symbol();
```

- Symbol은 항상 고유하며, 두 개의 Symbol값도 서로 다름

- 따라서 `모든 Symbol은 유일함`

<br/>

### 12.4.2 Symbol을 객체 프로퍼티 키로 사용

```javascript
const mySymbol = Symbol();

const myObj = {
  [mySymbol]: 'Hello, Symbol!',
};

console.log(myObj[mySymbol]); // 출력: "Hello, Symbol!"
```

- Symbol을 객체의 프로퍼티 키로 사용할 수 있음

- 이로 인해 객체의 프로퍼티가 다른 프로퍼티와 충돌하지 않고 고유한 식별자를 갖게 됨

<br/>

### 12.4.3 Symbol의 설명(Description)

```javascript
const mySymbol = Symbol('My Symbol Description');
```

- Symbol 생성 시 선택적으로 설명(Description)을 제공할 수 있음

- 설명은 Symbol을 디버깅하거나 이해하기 쉽게 만듦

<br/>

### 12.4.4 전역 Symbol 레지스트리(global symbol registry)

```javascript
const mySymbol1 = Symbol.for('sharedSymbol');
const mySymbol2 = Symbol.for('sharedSymbol');

console.log(mySymbol1 === mySymbol2); // true
```

- 전역 Symbol 레지스트리를 사용해 공유할 수 있음

- 이를 통해 동일한 Symbol을 여러 곳에서 사용할 수 있음

<br/>

<details>
  <summary><b>[참고] 전역 Symbol 레지스트리(global symbol registry)</b></summary>

- JavaScript에서 Symbol값을 공유하고 재사용할 수 있는 `중앙 저장소`

- 이 레지스트리는 Symbol값과 관련된 문자열 식별자를 매핑하여 Symbol값을 저장하고 공유하는 역할을 함

- Symbol 생성 시 `Symbol.for()` 메서드 사용 시 해당 Symbol이 레지스트리에 등록되고, 동일한 문자열 식별자로 생성한 다른 Symbol이 다른 Symbol값에 매핑됨

- 만약 레지스트리에 해당 문자열 식별자로 등록된 Symbol이 없으면 새로운 Symbol이 생성되며, 이미 등록된 경우 기존의 Symbol을 반환

- 레지스트리 사용 시 여러 곳에서 동일한 Symbol을 공유하고, 객체 간 통신 시 사용되는 문자열 식별자에 대한 중복을 방지할 수 있음

- 이는 특히 라이브러리나 프레임워크에 사용되어 일관성있는 동작을 유지하고 충돌을 방지하는데 도움이 됨

</details>

<br/>

### 12.4.5 내장 Symbol

- ES6에는 내장된 Symbol _(Symbol.hasInstance, Symbol.toStringTag 등)_ 이 있음

- 이들은 JavaScript 내부 동작과 관련이 있음

<br/>
