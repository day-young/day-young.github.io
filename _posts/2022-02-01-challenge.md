---
layout: post
title: Challenge
date: 2022-02-01 21:40 +0900
categories: [강의기록, U)Javascript]
tags: [challenge]
---

아주 작고 귀여운 챌린지부터 일단 기록 :pencil2:

## [220129] S2) 16. Challenge #1

Mark와 John이 BMI를 비교하려고 합니다. 각각 체질량계산 공식을 이용하여 계산하세요.  
BMI 계산 공식 : mass / height \*_ 2 = mass / (height _ height)

1. Mark's, John's mass와 height를 변수에 할당
2. 각각의 데이터로 BMI계산, 변수에 할당
3. markHigherBMI 란 이름의 변수 생성, Boolean 형태로 저장

```javascript
const marksWeights = 78; // massMark
const marksHeights = 1.69; //heightMark
const markBMI = marksWeights / marksHeights ** 2;
console.log(markBMI);

const johnsWeight = 92;
const johnsHeight = 1.95;
const johnsBMI = johnsWeight / johnsHeight ** 2;
console.log(johnsBMI);

const markHigherBMI = markBMI > johnsBMI;
console.log(markHigherBMI);
```

풀이 후 생각한 것 : 변수명을 좀 더 예쁘게.. :open_mouth:

## [220128] S2) 19. Challenge #2

Mark와 John이 BMI를 비교하려고 합니다. 챌린지 1에서 사용한 것을 기반으로 발전시키세요

1. if를 사용해서 BMI를 비교하고 콘솔에 출력합니다. "Mark's BMI is higher than John's!" or "John's BMI is higher than Mark's!"
2. 템플릿 리터럴을 사용해서 출력하세요. 예) "Mark's
   BMI (28.3) is higher than John's (23.9)!"

```javascript
//data1
const massMark = 78;
const heightMark = 1.69;
const massJohn = 92;
const HeightJohn = 1.95;
//data2
// const massMark = 95;
// const heightMark = 1.88;
// const massJohn = 85;
// const HeightJohn = 1.76;

const BMIMark = massMark / heightMark ** 2;
const BMIJohn = massJohn / HeightJohn ** 2;

if (BMIMark > BMIJohn) {
  console.log(`Mark's BMI (${BMIMark}) is higher than John's(${BMIJohn})!`);
} else {
  console.log(`John's BMI (${BMIJohn}) is higher than Mark's(${BMIMark})!`);
}
```
