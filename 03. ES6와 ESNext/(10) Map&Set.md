# 10. Map&Set

## 10.1 Map&Set의 등장 배경

1. 객체의 한계 극복

   - JavaScript의 객체는 문자열 또는 Symbol을 키로 사용해 다양한 데이터 타입을 값으로 저장할 수 있음

   - 그러나 `객체는 프로퍼티 순서를 보장하지 않고`, 프로퍼티를 순회할 때 모든 프로퍼티가 열거됨

   - 이로 인해 객체를 집합이나 맵처럼 사용하기 어려움

2. 중복 데이터 제거

   - 중복값을 저장할 수 있는 배열이나 객체와는 달리, Set은 중복값을 허용하지 않으므로 고유한 값을 관리하는데 유용함

<br/><br/>

## 10.2 Map

### 10.2.1 Map의 정의와 특징

- `키-값(key-value) 쌍을 저장하는 데이터 구조`

- `키의 데이터 타입 제한이 없음`

  - 어떤 데이터 타입도 키로 사용할 수 있음

  - 반면, 객체는 키에 문자열 또는 Symbol로만 제한됨

- `객체와 다른 별개의 데이터 구조임`

  - 따라서 객체와 충돌 없이 사용할 수 있음

- `순서를 보장함`

  - 데이터를 삽입한 순서대로 순회할 수 있어 순서가 중요한 경우 유용함

<br/>

### 10.2.2 Map의 장/단점

#### `장점`

- 키-값 쌍을 관리하기에 용이하며, 순서가 보장됨

- 다양한 데이터 타입을 키로 사용할 수 있음

- 중복된 키를 허용하지 않아 고유한 데이터를 저장할 수 있음

<br/>

#### `단점`

- 객체와 비교했을 때 일부 브라우저에서는 Map의 성능이 조금 떨어질 수 있음

<br/>

### 10.2.3 Map의 주요 메서드와 사용법

#### `한 눈에 보기`

```javascript
✨ 주요 메서드 및 프로퍼티

✔️ new Map() // 맵 생성
✔️ map.set(key, value) // key를 이용해 value 저장
✔️ map.get(key) // key에 해당하는 값을 반환, key가 존재하지 않으면 undefined 반환
✔️ map.has(key) // key가 존재하면 true, 존재하지 않으면 false 반환
✔️ map.delete(key) // key에 해당하는 값을 삭제
✔️ map.clear() // 맵 안의 모든 요소를 제거
✔️ map.size // 요소의 개수 반환
```

<br/>

#### `Map 생성`

```javascript
const myMap = new Map();
```

<br/>

#### `값 추가 및 수정`

```javascript
myMap.set('name', 'Eric'); // 키 'name'에 'Eric'을 추가 또는 업데이트
myMap.set('age', 30); // 키 'age'에 30을 추가 또는 업데이트
```

<br/>

#### `값 조회`

```javascript
console.log(myMap.get('name')); // 출력: "Eric"
```

<br/>

#### `값 삭제`

```javascript
myMap.delete('age'); // 키 'age'와 연관된 값을 삭제
```

<br/>

#### `크기 조회`

```javascript
console.log(myMap.size); // Map의 크기를 조회
```

<br/>

#### `순회`

```javascript
myMap.forEach((value, key) => {
  console.log(`${key}: ${value}`);
});

// 출력:
// "name: Eric"

for (const key of myMap.keys()) {
  console.log(key);
}

for (const value of myMap.values()) {
  console.log(value);
}

for (const entry of myMap.entries()) {
  console.log(`${entry[0]}: ${entry[1]}`);
}
```

- keys(), values(), entries() 메서드를 사용해 키, 값, 키-값 쌍을 반복(순회)할 수 있음

<br/><br/>

## 10.3 Set

### 10.3.1 Set의 정의와 특징

- `고유한 값을 저장하는 데이터 구조`

- `중복값을 허용하지 않음`

- 순서가 있는 유한집합을 나타내는데 유용함

<br/>

### 10.3.2 Set의 장/단점

#### `장점`

- 중복된 값을 허용하지 않으므로 고유한 값 목록 관리에 유용

- 데이터의 존재 여부를 빠르게 확인할 수 있음

<br/>

#### `단점`

- 키-값 쌍을 저장하지 않고 값만 저장하기 때문에 특정 값을 찾아내기 위해서는 순회가 필요함

<br/>

### 10.3.3 Set의 주요 메서드와 사용법

#### `Set 생성`

```javascript
const mySet = new Set();
```

<br/>

#### `값 추가`

```javascript
mySet.add('apple'); // 'apple'을 추가
mySet.add('banana'); // 'banana'를 추가
mySet.add('apple'); // 중복된 값이므로 무시됨
```

<br/>

#### `값 삭제`

```javascript
mySet.delete('banana'); // 'banana' 삭제
```

<br/>

#### `값 존재 여부 확인`

```javascript
console.log(mySet.has('apple')); // true
```

<br/>

#### `크기 조회`

```javascript
console.log(mySet.size); // Set의 크기를 조회
```

<br/>

#### `순회`

```javascript
mySet.forEach((value) => {
  console.log(value);
});

// 출력:
// "apple"
```
