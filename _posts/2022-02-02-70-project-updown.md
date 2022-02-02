---
layout: post
title: 70. PROJECT
categories:
- 강의기록
- U)Javascript
tags:
- challenge
date: 2022-02-02 21:03 +0900
---
## 70. PROJECT #1: 숫자 맞추기 (UpDown)

페이지에서 임의로 생선된 숫자를 사용자가 맞추는 게임  
수는 1부터 20까지, 체크당 스코어 1점 감소되며, 가장 빨리 맞췄을 때 남은 점수가 하이스코어로 기록된다

### HTML 구조와 화면

<a href="https://ibb.co/3dP4T4v"><img src="https://i.ibb.co/zxtQmQF/K-20220202-728731.png" alt="K-20220202-728731" border="0"></a>


### Javascript

#### 변수 선언

```javascript
let secretNumber = Math.trunc(Math.random() * 20) + 1;
let score = 20;
let highScore = 0;
```

- `secretNumber` : 1부터 20까지 생성되는 무작위 수로 사용자가 맞춰야 할 수
- `score`: 20점부터 시작하며 한번 check할 때 마다 1점씩 감소한다.
- `highscore`: 사용자가 `secretNumber`를 가장 빨리 맞췄을 때 기록된다.

#### 시나리오 로직

INPUT.guess에 값을 입력하고 BUTTON.check을 누르면 로직 시작

  + 동률일 경우 `score를` `highScore와` 비교하여 초과일때만 highScore에 표시/배경화면 색 변경

  + 추측한 수가 랜덤수와 같을 때: 배경 색 변경, 메세지 변경, 숫자 표시 및 너비 증가

  + 추측한 수 > 랜덤수가 다를 때: `guess > secretNumber`로 비교하여 `true`일때 'Too high' `false`일때 'Too Low' 출력(삼항연산자 사용)
  + 동시에 `score` 1씩 감소, `score가` 1이되면 게임 종료, 메시지 변경

```javascript
document.querySelector(".check").addEventListener("click", function () {
  const guess = Number(document.querySelector(".guess").value);

  if (!guess) {
    // 아무 값이 없을때
    displayMessage("🤔 No number!");
  } else if (guess === secretNumber) {
    // 플레이어가 이겼을 때
    displayMessage("🎉 Correct Number!");
    document.querySelector(".number").textContent = secretNumber;
    document.querySelector("body").style.backgroundColor = " #60b347";
    document.querySelector(".number").style.width = "30rem"; // rem을쓰기위해 문자열로

    // 5) 하이스코어 기능
    if (score > highScore) {
      highScore = score;
      document.querySelector(".highscore").textContent = highScore;
    }
  } else if (guess !== secretNumber) {
    // 제출 숫자가 secretNumber와 다를 때
    if (score > 1) {
      displayMessage(guess > secretNumber ? "📈 Too high!" : "📉 Too Low!");
      score--;
      document.querySelector(".score").textContent = score;
    } else {
      displayMessage("😡 You lost the game!");
      document.querySelector(".score").textContent = 0;
    }
  }
});
```

#### again 버튼 이벤트 처리

(챌린지였던것)  
플레이어가 새로운 추측을 할 수 있도록 기능을 구현하십시오!

1. 'again' 클래스가 있는 요소를 선택하고 클릭 이벤트 핸들러를 연결합니다.
2. 핸들러 기능에서 'score' 및 'secretNumber' 변수의 초기 값을 복원합니다.
3. 메시지, number, score 및 추측 입력 필드의 초기 조건을 복원합니다.
4. 또한 원래 배경색 (#222)과 숫자 너비 (15rem)를 복원합니다.

```js
document.querySelector(".again").addEventListener("click", function () {
  score = 20;
  secretNumber = Math.trunc(Math.random() * 20) + 1;
  document.querySelector(".score").textContent = score;
  displayMessage("Start guessing...");
  document.querySelector(".guess").value = "";
  document.querySelector(".number").textContent = "?";
  document.querySelector(".number").style.width = "15rem";
  document.querySelector("body").style.backgroundColor = "#222";
});
```

#### 중복코드 제거 및 포인트

```js
const displayMessage = function (message) {
  document.querySelector(".message").textContent = message;
};
```

(이미 강의들으면서 로직내에선 변경한 함수로 반영됐지만) document.querySelector('.message').textContent 로 메세지가 자주 변경되기 때문에 바꿀 메세지 내용을 인자로 받는 함수로 변경해서 호출하는 방법으로 변경. 대략 5번 정도 호출되었다..!   
또, inpuit이 Number일때는 value="";로 값을 변경한다는 것. .textContent만 쓰다가 왜 변경이 안되지 했던 기억이. 추가로 style메서드로 #, rem, px같은 단위를 쓸 땐 `' '`로 묶어줄 것.

