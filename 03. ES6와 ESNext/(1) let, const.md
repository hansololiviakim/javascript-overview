# 1. let, const

## 1.1 선언과 할당

### 선언

- 변수 명을 자바스크립트 엔진에 알리는 것

<br/>

### 할당

- 변수에 값을 저장하는 것(`=` 할당 연산자)

<br/><br/>

## 1.2 var의 특징

```javascript
var name = 'name1';
console.log(name); // name1

var name = 'name2';
console.log(name); // name2
```

- 재할당 가능

- 재선언 가능

<br/><br/>

## 1.3 let, const의 특징

### 1.3.1 let

```javascript
let value = 'value1';
console.log(value); // value1

value = 'value2'; // 재할당 가능
console.log(value); // value2

let value = 'value3'; // 재선언 불가능, SyntaxError: Identifier 'value' has already been declared
```

- 재할당 가능

- 재선언 불가능

<br/>

### 1.3.2 const

```javascript
const value; // 초기값 없이 선언 불가능, SyntaxError: Missing initializer in const declaration
---
const value = "value1"
console.log(value) // value1

value = "value2" // 재할당 불가능, TypeError: Assignment to constant variable.

const value = "value2" // 재선언 불가능, SyntaxError: Identifier 'value' has already been declared
```

- 재할당, 재선언 불가능

- 초기값이 없을 경우 선언 불가능

<br/><br/>

## 1.4 let, const의 호이스팅

- [02 > 1) > (1) 변수와 상수 참조](https://shorturl.at/sEF09)
