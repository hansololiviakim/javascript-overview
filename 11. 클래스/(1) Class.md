# 1. Class

## 1.1 정의

- JavaScript의 객체 지향 프로그래밍을 지원하기 위한 기능 중 하나

- 클래스는 `객체를 생성하기 위한 템플릿`으로, `객체의 구조와 동작을 정의`하는데 사용됨

- 클래스 사용 시 객체를 더 쉽게 생성하고 관리할 수 있음

- 또한 코드를 객체 지향적으로 구성하고 객체 간의 관계를 나타내기 쉽게 만들 수 있음 _(코드를 더 모듈화할 수 있음)_

- 코드의 가독성과 재사용성을 향상시킴

<br/><br/>

## 1.2 클래스 정의 순서 및 특징

### 1.2.1 클래스 정의

```javascript
class Person {
  // 클래스 내용
}
```

- `class` 키워드를 사용해 클래스 정의

- 이 단계에서는 클래스의 기본 구조 정의

- `클래스 이름은 대문자`로 시작하며, 생성자 함수와 구별하기 위함

<br/>

### 1.2.2 생성자 메서드 정의

```javascript
class Person {
  constructor(name, age) {
    this.name = name;
    this.age = age;
  }
}
```

- `constructor` 메서드를 클래스 내에 정의하여 객체 초기화 처리

- 생성자 메서드는 객체가 생성될 때 자동으로 호출됨

<br/>

### 1.2.3 메서드 정의

```javascript
class Person {
  constructor(name, age) {
    this.name = name;
    this.age = age;
  }

  sayHello() {
    console.log(`안녕하세요, 제 이름은 ${this.name}이고, 나이는 ${this.age}세입니다.`);
  }
}
```

- 클래스 내부에 필요한 메서드 정의

- 해당 메서드는 클래스의 동작을 구현하는 데 사용됨

<br/>

### 1.2.4 객체 생성

```javascript
const person1 = new Person('Eric', 30);
const person2 = new Person('Hansol', 25);

person1.sayHello(); // 출력: "안녕하세요, 제 이름은 Eric이고, 나이는 30세입니다."
person2.sayHello(); // 출력: "안녕하세요, 제 이름은 Hansol이고, 나이는 25세입니다."
```

- `new` 키워드를 사용해 클래스에서 객체 생성

- 생성자 메서드에 전달된 인수를 사용해 객체 초기화

<br/>

### 1.2.5 상속 설정

```javascript
class Student extends Person {
  constructor(name, age, grade) {
    super(name, age); // 부모 클래스의 생성자 호출
    this.grade = grade;
  }

  study() {
    console.log(`${this.name}이(가) 공부합니다.`);
  }
}
```

- 필요한 경우 클래스를 상속하거나 하위 클래스를 만들 수 있음

- 이를 통해 부모 클래스의 속성과 메서드를 상속하고 추가적으로 확장할 수 있음
