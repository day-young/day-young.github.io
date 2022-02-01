---
layout: post
title: 변수와 값
date: 2022-02-01 20:33 +0900
categories: [Blogging, Javascript]
tags: [Javascript, value]
---

`head` 혹은 `</body>` 위에 넣는다

## Values and Variables 값과 변수

값은 Object와 primitive로 나뉜다.

### Primitive Data types 원시 자료형

- Number : 부동소수로 정수와 소수

```javascript
let age = 24;
let weight = 45.7;
```

- String : 문장, 글자, 텍스트

```javascript
let firstName = "John";
```

- Boolean : 논리유형으로 `true` 혹은 `false`만 가능

```javascript
let driverLicense = false;
```

- Underfined: 변수는 선언했지만 값이 정의되지 않은 상태(empty value)

```javascript
let phoneNumber;
```

- Null
- Symbol, BigInt...

### Dynamic typing 동적타이핑

자바스크립트는 변수의 수동으로 명시하지 않아도 가변적으로 값을 지정할 수 있으며 자료형은 자동으로 처리된다.

### Indicating the type of value 변수 자료형 확인하기

```javascript
console.log(typeof year);
```

#### Variable name conventions 변수명 짓기 규칙

- camelCase로 네이밍
- 첫글자 숫자 사용불가
- 특수문자는 `_`, `&`만 가능
- 예약어 사용불가

## let, const and var 변수의 선언

`let` : 변수 값이 바뀔 가능성이 있을때 사용한다. 추후 재할당이 가능하다  
`const` : 상수. 변수의 값이 바뀌지 않을때 사용한다. 재할당이 불가하며 기본적으로 초기 값이 필요하다  
`var` : 기본적으로 변수를 정의하는 오래된 방법(작동함)
